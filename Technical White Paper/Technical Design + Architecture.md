The technical design for SocialChains consists of smart contracts (which are powered by blockchain) that are integrated within a full-stack web architecture. 
We plan to write the smart contracts using the programming language Solidity, which can be run on the Ethereum virtual machine to simulate transactions 
between an influencer and any companies that they have partnered with. Ultimately, all of the smart contracts will be stored on the SocialChains blockchain. 
This process can be visualized in the diagram below:

<p align="center">
  <img src="Images/Blockchain Flow.PNG" width="600" height="500"/>
</p>

In order to coalesce the smart contracts within our website, we plan to utilize the Azure Blockchain Workbench. This platform uses Azure Storage to store 
metadata on the cloud, which would enable us to easily query data about the smart contracts using the Azure SQL Database. The database will be connected to 
the back-end of the web application, which will be created through Node.js, NPM, and the Express framework. The front-end will be constructed with React.js, 
Redux, and Sass. All of these components can be visualized in the diagram below:

<p align="center">
  <img src="Images/Technical Flow.PNG" width="600" height="500"/>
</p>

As an overview of the technical architecture behind SocialChains, the front-end (or web interface) of the application will display user dashboards, both for 
the influencer and the company. These dashboards will contain information about follower / viewer analytics and all partnerships. The smart contract between 
an influencer and a company will be sent to the SocialChains blockchain network once finalized by both parties, and its contents will be stored within the 
Azure SQL database. Any future updates to the smart contract will concurrently be reflected in the front-end interface as well as the database. Ultimately, 
the back-end (or web server) will host the web interface. It will also act as the intermediary between the front-end interface and the smart contracts that 
are stored in the database. 
