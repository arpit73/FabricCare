# FabricCare
 One stop solution to cease fraud and black marketing of the donated organs using hyperledger fabric
 * Organ waiting list made transparent to cease jumping and manipulations.
 * Organ availability list made transparent and updated by the hospitals.
 * Total privacy for the donor.
 * Tracking the organ is possible.
 * No black marketing of the organs to the rich.

# Usage
A blockchain enabled product for tracking organs all over the country and eliminate the organ black market in India.

Organ donation is a very important for saving someone’s life. It is estimated that 42% of transplanted organs come from illegal trafficking in organs. In India organs can come at a cost of some poor person having to sell their kidney to make some money or have it operated out of them without consent. The black market for organs is a big issue that can be difficult to track since these organs may make to legitimate channels. 

By using our blockchain based tracking system we can eliminate the possibility of illegitimately obtained organs making it into the hospitals.

Usage: In case of a death, if the person is an organ donor we log all the relevant medical details about the patient and the organs obtained, these are then logged into our system which is decentralised and thus the log is written into to blockchain based ledger that cannot be modified later.
When an entry is made into ledger it is observed by everyone using the system thus alerting everyone of a new organ. When a hospital receives that organ they can track its history and thus be sure that it was legitimately obtained. They will then log all the details about how they came to get the organ and what the new location is, then finally update it when it is transplanted into another person. This creates a immutable trail that any hospital can use to determine the history of an organ.

If an organ goes missing from a hospital it will not be logged be through legitimate means and thus if a hospital observes any discrepancy in the data they will simply not accept it and alert the authorities about the crime.

 # Screencaps Of Fabric Care
 ## 1. Home page
 ![Alt text](Screens/homeScreen.png?raw=true)
 ## 2. Organs Form
 ![Alt text](Screens/organForm.png?raw=true)
 ## 3. Donor Form
 ![Alt text](Screens/donorForm.png?raw=true)
 ## 4. Organ Lists
 ![Alt text](Screens/organFullList.png?raw=true)

 ![Alt text](Screens/organsList.png?raw=true)
 ## 5. Waiting List
 ![Alt text](Screens/waitingList.png?raw=true)
 # Steps to run Fabric Care
 ## 1. Run shell scripts from fabric tools
 ### 1. Run Fabric netwok
 ```
 cd fabric-tools
 ./startFabric.sh
 ```
 ### 2. create a PeerAdminCard
 ```
 ./createPeerAdminCard.sh
 ```
 ## 2. Install node packages
 ```
 npm install
 ```
 ## 3. Create the BNA archive
 ```
 composer archive create  --sourceType dir --sourceName ../
 ```
 ## 4. Install a network using archive file
 ```
 composer network install -a ./fabric-care@0.0.1.bna -c PeerAdmin@hlfv1
 ```

 ## 5. Start a network 
 ```
 composer network start -c PeerAdmin@hlfv1 -n fabric-care -V 0.0.1 -A admin -S adminpw
 ```

 ## 6. Import the card generated in above step
 ```
 composer card import -f admin@fabric-care.card
 ```
 ## 7. Final step
 ```
 node app.js
 ```

 # Steps To setup or Integrate Hyperledger Fabric
 ## 1. Install the CLI tools
 ### 1. Essential CLI tools:
 ```
 npm install -g composer-cli
 ```
 ### 2. Utility for running a REST Server on your machine to expose your business networks as RESTful APIs:
 ```
 npm install -g composer-rest-server
 ```
 ### 3. Useful utility for generating application assets:
 ```
 npm install -g generator-hyperledger-composer
 ```
 ### 4. Yeoman is a tool for generating applications, which utilises generator-hyperledger-composer:
 ```
 npm install -g yo
 ```
 ## 2. Install playground or use online  [Composer playground](https://composer-playground.mybluemix.net)
 Browser app for simple editing and testing Business Networks:
 ```
 npm install -g composer-playground
 ```
 ## 3. Install Hyperledger Fabric
 This step gives you a local Hyperledger Fabric runtime to deploy your business networks to.
 ### 1. In a directory of your choice (we will assume ~/fabric-tools), get the .tar.gz file that contains the tools to install Hyperledger Fabric:
 ```
 mkdir ~/fabric-tools && cd ~/fabric-tools

 curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz
 tar -xvf fabric-dev-servers.tar.gz
 ```
 ### 2. Use the scripts you just downloaded and extracted to download a local Hyperledger Fabric runtime:
 ```
 cd ~/fabric-tools
 ./downloadFabric.sh
 ```
 ## 4. Create a BNA file using YEOMAN framework
 ```
 yo hyperledger-composer:businessnetwork
 ```

 ## Prerequisities
 * Python 2.7
 * Nodejs and npm with node version 8.11.1
 * Docker Engine: Version 17.03 or higher
