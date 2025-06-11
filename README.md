# Farm2Fork-Hyperledger
Blockchain-based supply chain tracking using Hyperledger Composer

##  The proposed system utilizes Hyperledger Fabric to create a blockchain based food supply chain that ensures transparency, traceability, and security in 
food transactions. Unlike the traditional system, where data is isolated and  manipulated by intermediaries, this system records every transaction in an 
immutable distributed ledger. 

Key Features: 
1. Decentralized and Transparent Tracking: All transactions (e.g., farming, transportation, warehousing, and retail) are stored on a blockchain ledger. Every stakeholder (Farmer, Distributor, Retailer, 
Consumer) can access verified product information. 
2. Hyperledger Composer for Smart Contracts: Smart contracts automate processes such as payments, contract execution, and shipment verification. Transactions like "CreateProduct," "CreateShipment," and "ProductOwnerChange" ensure real-time updates on product status. 
3. Web-Based Explorer & Application: A REST API and web-based UI allow participants to interact with the blockchain ledger. Farmers, distributors, and retailers can add or update data, 
view transactions, and track products. 
4. Enhanced Food Safety & Quick Recalls: In case of contamination, affected batches can be traced instantly, reducing response time and minimizing risks.


In our Farm2Fork Project using Hyperledger Composer, the Models within the Business Network represent the core entities (Participants, Assets, and Transactions) that interact on the blockchain. 

1. Participants: 
These are the people or organizations involved in the supply chain. Each has specific roles and permissions. 
o Farmers – Create and own products (e.g., vegetables, grains). 
o Distributors – Purchase and transport products from farmers to retailers. 
o Retailers – Buy from distributors and sell to end consumers. 
o Shippers – Handle transportation and update shipment status. 
o Warehouses – Store products temporarily before final delivery. 

2. Assets: 
Assets are valuable items being tracked and transacted within the network. 
o Product – The item grown or made by the farmer (e.g., rice, wheat). 
o Shipment – Represents the movement of products from one participant to 
another. 
o Contract – Defines the agreement between participants (like delivery terms, 
product types, cost, etc.). 

3. Transactions: 
Transactions change the state of assets or participants in the blockchain. They are 
recorded immutably. 
o Create Product – A farmer adds a new product to the network. 
o Create Contract – An agreement is created between parties (e.g., farmer 
and distributor). 
o Create Shipment – A shipment is initiated based on an existing contract. 
o Update Shipment Status – A shipper updates the current state (e.g., 
dispatched, in transit, delivered) of the shipment.

This business network model ensures transparency, security, and traceability throughout the supply chain. It consists of participants like farmers, distributors, retailers, and warehouses, along with assets such as products, shipments, and contracts. Transactions like product creation, shipment tracking, and contract management are executed via Hyperledger Composer. Implemented using Concerto (.cto) files, the system is managed through a web UI or REST API, enabling efficient and decentralized monitoring of farm products from source to consumer, ensuring trust and accountability.



![Screenshot 2025-06-11 185206](https://github.com/user-attachments/assets/fe301c36-86f7-4572-9c6c-4d240828e2b5)



SMART CONTRACT EXICUTION 


![Screenshot 2025-06-11 185309](https://github.com/user-attachments/assets/e8e3abc5-6330-4ca7-986e-3b39f7ae4691)


##  OUTPUTS

farm2fork app at    local host:4200


![Screenshot 2025-06-11 185436](https://github.com/user-attachments/assets/9d78772d-2fd6-4258-831c-591d9ba1e509)



Creating participants within the app



![Screenshot 2025-06-11 185713](https://github.com/user-attachments/assets/7c40c259-6c9b-430a-9d91-44f612ec2648)



![Screenshot 2025-06-11 190025](https://github.com/user-attachments/assets/c8fb2dc4-a50a-477d-b189-8dacd6bdced5)



![Screenshot 2025-06-11 190025](https://github.com/user-attachments/assets/56d0dcfa-8bad-44e1-a376-3783b30c6de2)




![Screenshot 2025-06-11 190111](https://github.com/user-attachments/assets/307b919f-87c2-4044-9be5-6e918170954d)





![Screenshot 2025-06-11 190145](https://github.com/user-attachments/assets/c952fcda-0699-4e31-af86-b7e888df4c8b)





Records of Transactions


![Screenshot 2025-06-11 190216](https://github.com/user-attachments/assets/7e2a7e3a-1f3c-4380-9796-22f242f0c4d6)




