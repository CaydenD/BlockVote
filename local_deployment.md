# Local Deployment of blockchain dapp

# pre reqs


# Steps to start up

## Step 1. Clone the Repo (If first time set up)

Git clone this repo onto your computer in the destination of your choice, then go into the web-app folder:

## Step 2. Make sure docker is running

## Step 3. Start local fabric runtime
- Open ibm bc vscode extension under fabric environments and click on 1 org local fabric to start your local fabric network

## Step 4. (If first time set up or making changes to the smart contract) import, install, and instantiate smart contract 
- On mac open the command palette(shift + common + p)
- Once the command palette is open choose IBM Blockchain Platform: Import a Package. From here select the contract directory from the project (evote/contract) and then choose the contract, in our case voterContract@7.0.0.cds

## Step 5. (If first time set up) export connection details
- Open ibm bc vscode extension under fabric gateways and click on 1 org gateway to connect with the gateway using the admin identity
- Once connected as an admin select the three dots next to fabric gateways and from the dropdown choose export connection profile. Save this file to evote/web-app/server/fabric_connection.json

## Step 6. (if first time set up) export local wallet
- under the fabric wallets pannel right click the 1 org wallet and choose export wallet. export his wallet to the following location /evote/web-app/server/wallet.

#### Update Config

Next, update the `config.json` found in your evote/web-app/server file so it looks like this:

```json
{
  "connection_file": "fabric_connection.json",
  "appAdmin": "admin",
  "appAdminSecret": "adminpw",
  "orgMSPID": "Org1MSP",
  "caName": "ca.org1.example.com",
  "userName": "V1",
  "gatewayDiscovery": { "enabled": true, "asLocalhost": true }
} 
```

this is making the admin identity stored in the wallet be the one which will be sign to all of our transactions. This also lets the network know that our given identiy is the one partaking in a given transaction which was first signed by the certificate authority(ca.1org.example.com)

## Step 7. starting the server(node.js) and front end client(vue.js)

- (if first time set up) install dependencies for both front end and back end
- in the server directory evote/web-app/server and evote/web-app/client run npm install to get all the dependencies
- then start the server from evote/web-app/server with npm start which will execute the start script in the servers package.json file
- then start the client from evote/web-app/client with npm run serve which will execute the serve script in the clients package,json file
- if all goes well you should have a running version of the dapp running on your machine locally at port 8080 or if you have changed the desried port then at whatever port was specifed
