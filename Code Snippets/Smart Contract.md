The following code is a sample blockchain smart contract on the SocialChains platform -- it describes a brand partnership between a company and an influencer. The smart contract is written in the programming language Solidity and can ultimately be run on the Ethereum virtual machine!

```
pragma solidity ^0.4.0; 

contract brandPartnership { 
  uint totalReceived = 0; 
  address company; 
  mapping (address => uint) public commissionAmount; 
  mapping (address => uint) public withdrawnCommission; 
  function brandPartnership() payable public { 
    updateTotalReceived(); 
    company = msg.influencer;
  } 

  function () payable public {
    updateTotalReceived();
  }

  function updateTotalReceived() internal {
    totalReceived += msg.value;
  }

  function addAddress(address _commissionAddress, uint _commission) isCompany public {
    if (msg.influencer == company) {
      commissionAmount[_commissionAddress] = _commission;
    }
  }

  modifier isCompany() {
    require(msg.influencer == company);
    _;
  }

  modifier canWithdraw() {
    require(commissionAmount[msg.influencer] > 0);
    _;
  }

  function withdraw() canWithdraw public  {
    uint amountPaid = withdrawnCommission[msg.influencer];
    uint influencerCommission = commissionAmount[msg.influencer];
    uint commissionToPay = influencerCommission - amountPaid;

    if (commissionToPay > 0) {
      withdrawnCommission[msg.influencer] = amountPaid + commissionToPay;
      msg.influencer.transfer(commissionToPay);
    }
  }
}
```
