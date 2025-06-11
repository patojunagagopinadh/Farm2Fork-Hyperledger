Ubuntu 18.04 plays a crucial role in the development and deployment of the Farm2Fork project, providing a stable and secure environment for blockchain
based food traceability. Since Ubuntu is widely used for Hyperledger Fabric and Hyperledger Composer, it ensures seamless execution of smart contracts and 
blockchain operations. The open-source nature of Ubuntu allows for better customization and control over dependencies, making it ideal for setting up the 
Hyperledger Fabric network using Docker containers.


![Screenshot 2025-06-11 175403](https://github.com/user-attachments/assets/76b76e20-461c-422b-a8ec-b7bad2f16923)



Docker allows you to run Hyperledger Fabric in containerized 
environments. Containers make it easy to deploy and manage the blockchain 
network, ensuring that all services (e.g., peer nodes, orderers and chaincode) run 
in isolated and consistent environments. Moreover, Docker Engine depends 
on containerd and runc. Docker Engine bundles these dependencies as one 
bundle: containerd.io. If you have installed the containerd or runc previously, 
uninstall them to avoid conflicts with the versions bundled with Docker Engine. 
Oper terminal and Run the following command to uninstall all conflicting packages: 
➢ for pkg in docker.io docker-doc docker-compose docker-compose-v2 
podman-docker containerd runc; do sudo apt-get remove $pkg; done 
Before you install Docker Engine for the first time on a new host machine, 
you need to set up the Docker apt repository. Afterward, you can install and 
update Docker from the repository. Run following commands 
# Add Docker's official GPG key: 
➢ sudo apt-get update 
➢ sudo apt-get install ca-certificates curl 
➢ sudo install -m 0755 -d /etc/apt/keyrings 
➢ sudo chmod a+r /etc/apt/keyrings/docker.asc 
➢ sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o 
/etc/apt/keyrings/docker.asc 
# Add the repository to Apt sources: 
17 
[arch=$(dpkg --print-architecture) 
➢ echo \ 
➢ "deb 
signed
by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \ 
➢ $(. 
/etc/os-release 
&& 
echo 
"${UBUNTU_CODENAME:
$VERSION_CODENAME}") stable" | \ 
➢ sudo tee /etc/apt/sources.list.d/docker.list > /dev/null 
➢ sudo apt-get update



![Screenshot 2025-06-11 175816](https://github.com/user-attachments/assets/98b1a8fb-4768-4b81-aeaf-e1c01431a21c)



![Screenshot 2025-06-11 175900](https://github.com/user-attachments/assets/cdade439-c022-463d-a999-52c601e13c73)


sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx
plugin docker-compose-plugin  
Verify that the installation is successful by running the hello-world image


![Screenshot 2025-06-11 175927](https://github.com/user-attachments/assets/dc3fbd13-8b0b-41c8-a67b-82150e7edb15)



Docker-Compose automates the setup of multiple interconnected containers 
required by Hyperledger Fabric, such as CA, peers, and orderer nodes. Simplifies 
managing the entire network setup using docker-compose.yaml files. 
Run the following command to install Docker-Compose 
➢ sudo apt update 
➢ sudo apt install docker-compose



![Screenshot 2025-06-11 175944](https://github.com/user-attachments/assets/b549e596-7d50-49c6-8dcf-50302b394d02)



Check versions of docker and docker-compose using following command 
➢ docker –version && docker-compose –version


![Screenshot 2025-06-11 180007](https://github.com/user-attachments/assets/9d0ea984-1fc5-4728-8e52-37fbf88ce8f2)



To run Hyperledger Composer and Hyperledger Fabric, we need at least 4Gb of 
memory. 
Run the following commands to install Hyperledger Composer Pre-requisites 
➢ curl -O https://hyperledger.github.io/composer/latest/prereqs-ubuntu.sh 
➢ chmod u+x prereqs-ubuntu.sh 
➢ ./prereqs-ubuntu.sh


![Screenshot 2025-06-11 180026](https://github.com/user-attachments/assets/56d5450d-44c9-44e6-a530-c7c51ea39149)



![Screenshot 2025-06-11 180041](https://github.com/user-attachments/assets/74857826-287c-4c92-9134-c0564b7c1b13)



Prerequisites are essential to ensure the proper installation and functioning of 
software dependencies required for a project. In the case of our Farm2Fork 
20 
project, prerequisites like Node.js, npm, Docker, Docker Compose, and Python 
provide the necessary environment for running Hyperledger Composer. 
1. Node.js & npm – Required for running JavaScript-based applications and 
managing packages. 
2. Docker & Docker Compose – Essential for containerizing and managing 
blockchain components efficiently. 
3. Python – Supports script execution and dependency management.

A well-configured development environment is crucial for building, testing, 
and deploying software efficiently. It ensures that all necessary tools, 
dependencies, and frameworks are properly installed, minimizing compatibility 
issues. In the case of Hyperledger Composer, setting up tools like composer-cli, 
composer-rest-server, and generator-hyperledger-composer enables developers 
to create, manage, and interact with blockchain networks. The development 
environment also includes playgrounds for testing business logic and IDE support 
for efficient coding. By establishing a stable development environment, developers 
can streamline the workflow, improve debugging, and enhance collaboration, 
leading to a more efficient and error-free blockchain application deployment. 
Use following command to Install Essential CLI tools: 
➢ npm install -g composer-cli@0.20



![Screenshot 2025-06-11 180056](https://github.com/user-attachments/assets/2ec584c5-b55e-4cbe-99e4-b3b8215704dd)



![Screenshot 2025-06-11 180107](https://github.com/user-attachments/assets/bd633030-0347-4a37-bf72-df13a1787434)


Use following command to Install composer-rest-server 
➢ npm install -g composer-rest-server@0.20 
Utility for running a REST Server on our machine to expose our business networks 
as RESTful APIs:


![Screenshot 2025-06-11 180121](https://github.com/user-attachments/assets/270e3e97-2cfd-4d1d-8dab-856a79cc34f9)



![Screenshot 2025-06-11 180136](https://github.com/user-attachments/assets/b34a7287-5654-4a61-a76b-354d9c65e14b)



Use following command to Install generator 
➢ npm install -g generator-hyperledger-composer@0.20 
Useful utility for generating application assets: 


![Screenshot 2025-06-11 180156](https://github.com/user-attachments/assets/a03b5d14-ff4b-454a-a82f-ba2b1dcacde6)



![Screenshot 2025-06-11 180218](https://github.com/user-attachments/assets/89cb8089-7082-4074-8a6c-d6be7b959e7b)



Use following command to Install yeoman 
➢ npm install -g yo@1.8.1 
Yeoman is a tool for generating applications, which utilises generator-hyperledger
composer:


![Screenshot 2025-06-11 180230](https://github.com/user-attachments/assets/a4d3e7d5-e3f7-4a80-ba49-6d0a20cc6972)


![Screenshot 2025-06-11 180255](https://github.com/user-attachments/assets/609b9eb6-e70d-4286-86bc-3049df0f6db9)


Here choose “Bash config file (~/.bashrc)” to setup the completion script


![Screenshot 2025-06-11 180309](https://github.com/user-attachments/assets/f3c4ab2e-b7a1-4ecb-a304-88e602364142)


Use following command to Install composer-playground 
➢ npm install -g composer-playground@0.20 
It is a browser app for simple editing and testing Business Networks:



![Screenshot 2025-06-11 180324](https://github.com/user-attachments/assets/9bf8212b-e178-4561-96a7-2d06afb71e5b)



![Screenshot 2025-06-11 180351](https://github.com/user-attachments/assets/fbe2bb05-4221-4aed-b886-62cadbe7a2e3)



Run the following commands to install Hyperledger Fabric 
➢ mkdir ~/fabric-dev-servers && cd ~/fabric-dev-servers 
➢ curl -O 
https://raw.githubusercontent.com/hyperledger/composertools/master/packa
 ges/fabric-dev-servers/fabric-dev-servers.tar.gz 
➢ tar -xvf fabric-dev-servers.tar.gz


![Screenshot 2025-06-11 180518](https://github.com/user-attachments/assets/e0b09ace-8d28-418d-b6c8-f03e415d36fd)


➢ cd ~/fabric-dev-servers 
➢ export FABRIC_VERSION=hlfv12 
➢ ./downloadFabric.sh


![Screenshot 2025-06-11 180531](https://github.com/user-attachments/assets/9f3cc74e-65fc-4bff-8917-873466a7faec)


Now we successfully installed hyperledger fabric, to run fabric we need to update 
“docker compose.yaml” file by adding some lines


![Screenshot 2025-06-11 180543](https://github.com/user-attachments/assets/1439fcd8-a0fe-480c-b669-6b7ada4ed098)


![Screenshot 2025-06-11 180618](https://github.com/user-attachments/assets/103fccb6-4d00-41d2-a370-9df3e133aceb)


Open “docker compose.yaml” file add the lines “GODEBUG=netdns=go” at end of 
environment as shown in the figure. 


Here we need to follow some guidelines while entering and exiting the fabric 
environment. We need to follow the following commands to enter fabric 
environment 
➢ docker kill $(docker ps -q) 
➢ docker rm $(docker ps -aq) 
➢ rm -rf ~/.composer 
➢ cd fabric-dev-servers 
➢ ./startFabric.sh 
➢ ./createPeerAdminCard.sh

![Screenshot 2025-06-11 180637](https://github.com/user-attachments/assets/2ccb685a-2705-4574-9160-7039fbf28cf7)



![Screenshot 2025-06-11 180648](https://github.com/user-attachments/assets/33b4aa22-f1bc-44a0-a66b-7dc4227bf225)


After creating the peer admin card, we can do our work on project by exiting the   
environment with command “cd”. After completion of our work we need to follow 
some commands to stop the fabric 
➢ cd fabric-dev-servers 
➢ ./stopFabric.sh 
➢ ./teardownFabric.sh 
➢ cd 
➢ docker kill $(docker ps -q) 
➢ docker rm $(docker ps -aq) 
➢ rm -rf ~/.composer


![Screenshot 2025-06-11 180700](https://github.com/user-attachments/assets/67dce1af-e44d-452b-a762-43c7208a3362)



![Screenshot 2025-06-11 180728](https://github.com/user-attachments/assets/74485321-d99d-4eee-9d43-12b55ed1723f)


Now start the fabric and create peer admin card and run the following commands 
to generate business network file 
➢ cd 
➢ yo hyperledger-composer:businessnetwork  

Now make sure to follow the specifications in order to generate this file as shown 
In the image, we need to set up a business network using Hyperledger Composer. 


![Screenshot 2025-06-11 180743](https://github.com/user-attachments/assets/f2ca0699-55b9-4c07-a940-23f723656df9)



![Screenshot 2025-06-11 180801](https://github.com/user-attachments/assets/0267dc86-b002-463f-b282-6689ee490de8)


Now enter in to the directory and run the following commands to generate bna file. 
Make sure the files logic.js, permissions.acl, and models are perfect without any 
errors before generating the bna file 
➢ composer archive create -t dir -n  
➢ composer network install --card PeerAdmin@hlfv1 --archiveFile farm
fork@0.0.1.bna (to install business network) 
A BNA file (Business Network Archive) is a packaged archive used in Hyperledger 
Composer, containing all the necessary files to define a business network. It 
typically includes: 
• Model files (.cto): Define the data structures 
• Script files (.js): Contain the transaction logic 
• Access control files (permissions.acl): Define access rules 
This file is deployed to a Hyperledger Fabric blockchain to define the business 
logic and interactions. 


![Screenshot 2025-06-11 180904](https://github.com/user-attachments/assets/06e95bb2-200c-4b54-8485-6a1edfaf191b)



![Screenshot 2025-06-11 180911](https://github.com/user-attachments/assets/5e788fab-2882-4f08-85ae-8793f88addb2)



Run the following command to start business network 
➢ composer network start --networkName farm-fork --networkVersion 0.0.1 -
networkAdmin admin --networkAdminEnrollSecret adminpw --card 
PeerAdmin@hlfv1 --file networkadmin.card


![Screenshot 2025-06-11 180916](https://github.com/user-attachments/assets/d0cba0f1-e295-46cd-9100-d56b4e41fb48)


If you hit this error follow bellow commands else continue further process 
Run the following commands to solve the error


![Screenshot 2025-06-11 180921](https://github.com/user-attachments/assets/1d1424bc-2050-40a1-b9dd-43b710694ef8)


Enter the file directory and run following command 
➢ npm i -g composer-rest-server 
This will install composer-rest-server in the file directory


![Screenshot 2025-06-11 180926](https://github.com/user-attachments/assets/41b12402-b4ee-4a00-a2f2-4659e64220c2)




Now enter into the directory of composer-rest-server using bellow command and 
install swagger client 
➢ cd /home/student/.nvm/versions/node/v8. 17.0/lib/node_modules/composer
rest-server 
➢ npm install swagger-client@3.9.0


![Screenshot 2025-06-11 180932](https://github.com/user-attachments/assets/9b5b927c-cf63-42ed-acbe-f8a97f4d972c)



![Screenshot 2025-06-11 180937](https://github.com/user-attachments/assets/ba61877c-afca-4e5c-9a48-c5be1366779f)



Now run the following commands for chaincode execution 
➢ docker pull hyperledger/fabric-ccenv:amd64-1.4.4 
➢ docker tag hyperledger/fabric-ccenv:amd64-1.4.4 hyperledger/fabric
ccenv:latest



![Screenshot 2025-06-11 180944](https://github.com/user-attachments/assets/90c790a4-e5d6-4fbd-bca4-2771202d4af5)


Run the following commands to import networkadmin.card and ping to the 
business network name 
➢ composer card import --file networkadmin.card 
➢ composer network ping --card admin@farm-fork


![Screenshot 2025-06-11 180951](https://github.com/user-attachments/assets/6884833a-bf59-4c26-985f-74a6ea4e7141)




![Screenshot 2025-06-11 180956](https://github.com/user-attachments/assets/ae23d3eb-153b-40d6-8dd4-0a586e6f85d1)



1. composer card import --file networkadmin.card 
➢ Imports the business network admin card (networkadmin.card). 
➢ Allows the user to interact with the deployed business network. 
34 
➢ Assigns the card name admin@farm-fork. 
2. composer network ping --card admin@farm-fork 
➢ Tests the connection to the farm-fork business network using the imported 
admin card. 
➢ Verifies that the business network is running and accessible. 
➢ Displays Business network version (0.0.1) and Composer runtime version 
(0.20.9). Confirms the identity of the admin participant.


Run the following command to expose business network 
➢ composer-rest-server



![Screenshot 2025-06-11 181002](https://github.com/user-attachments/assets/2317c296-730c-46a3-aed9-c621cd3e0e54)




composer-rest-server 
Starts the Hyperledger Composer REST server for the farm-fork business 
network. It generates a REST API for interacting with the network. 
2. User Inputs During Setup: 
✓ Enter the name of the business network card to use: admin@farm-fork 
✓ Specify if you want namespaces in the generated REST API: never use 
35 
namespaces 
✓ Specify if you want to use an API key to secure the REST API: No 
✓ Specify if you want to enable authentication for the REST API using 
Passport: No 
✓ Specify if you want to enable the explorer test interface: Yes 
✓ Specify a key if you want to enable dynamic logging: 1 
✓ Specify if you want to enable event publication over WebSockets: Yes 
✓ Specify if you want to enable TLS security for the REST API: No 
3. Output Details: 
REST server runs on http://localhost:3000. 
API Explorer available at http://localhost:3000/explorer. 
This step exposes the business network as a RESTful API, making it easy to 
interact with through web applications.



![Screenshot 2025-06-11 182053](https://github.com/user-attachments/assets/d63973a9-9b62-4cac-9b2b-af0ec7168ae2)




Now without closing present terminal open new terminal and run the following 
command to create app  
➢ yo hyperledger-composer:angular


![Screenshot 2025-06-11 182124](https://github.com/user-attachments/assets/641e875d-da23-4594-92cf-dd45b33a301c)



![Screenshot 2025-06-11 182149](https://github.com/user-attachments/assets/ac399c5d-fe49-488a-8714-8850d1775e70)



Now enter into the app file directory run the following commands 
➢ cd farm2fork-app 
➢ npm start



![Screenshot 2025-06-11 182155](https://github.com/user-attachments/assets/e008b3f0-4a24-4b06-a387-8dead32ca311)



“npm start” is required to start the Angular application 



![Screenshot 2025-06-11 182206](https://github.com/user-attachments/assets/fe69a779-4df1-4b30-87eb-42d33daa76f1)





![Screenshot 2025-06-11 182228](https://github.com/user-attachments/assets/376b3cb7-18c6-48fc-affd-16dbd724baeb)




Run the following command to test the farm-fork app by opening Hyperledger 
composer playground directly 
➢ Composer-playground 
Hyperledger Composer Playground is a web-based interface for developing, 
testing, and deploying blockchain business networks using Hyperledger 
Composer. The command composer-playground starts the Playground API server 
on localhost:8080, enabling you to interact with your Farm2Fork business 
network visually.



![Screenshot 2025-06-11 182238](https://github.com/user-attachments/assets/37219a01-aa41-4696-bdf9-02234b0d8789)






![Screenshot 2025-06-11 182248](https://github.com/user-attachments/assets/cafda9cf-a86d-4f2b-9366-43b5a39efbd9)







![Screenshot 2025-06-11 182255](https://github.com/user-attachments/assets/75acf2d7-2bdd-41bf-9d2a-9e0a48bb62ad)



Creating participants in bussiness network


![Screenshot 2025-06-11 185601](https://github.com/user-attachments/assets/8e3674a1-f193-4a5a-b929-0361a8320487)




Records of transactions



![Screenshot 2025-06-11 185713](https://github.com/user-attachments/assets/49c77624-e3a9-421f-8dca-67f190ba3863)






