# WarrantyContracts

### Requirements
- Daml v2.4.0
- Daml SDK
- VS Code
- Postman

### 1. Clone this repository
```
git clone https://github.com/J4SSGG/daml-poc.git
cd daml-poc
```
### 2. Use Daml Studio to make changes

Execute the following command: 
```
daml studio
```
This will open a new VS Code window with your project folder loaded. Make any changes you want.
### Daml Start
Execute the following command: 
```
daml start
```
This will initilize the `Navigator` and `JSON Web API` (and will perfom some other things like building the Main.daml field). You can disabled the `Navigator` changing **start-navigator: false** in the **daml.yaml** file. We will not use the `Navigator` this time.

### Postman
While the `JSON Web API` is loading, open Postman. Import the **WarrantyContracts.postman_collection** into Postman. This will create a new Collection in your current workspace called "Daml".

Once the `JSON Web API` is loaded and running. Execute the `GET Parties` request. It should received a 200 OK response and only one party called "sandbox".

You can now execute the requests in order (from top to bottom). The steps are self-described, but in short, we are simulating this:
- Create two parties. One is for the company and the other is for the user or buyer.
- Execute the create command in the contract. This will "create" a "warranty contract" for a sold item. 
- Issue the "warranty contract" to the buyer. Now the buyer owns the warranty contract.
- The buyer raises a claim to its "warranty contract".