# Local Deployment of blockchain dapp

# pre reqs


# Steps to start up

## Step 1. Clone the Repo (If first time set up)

Git clone this repo onto your computer in the destination of your choice, then go into the web-app folder:

## Step 2. Make sure docker is running

## Step 3. Start local fabric runtime

## Step 4. Start local fabric runtime
- Open ibm bc vscode extension under fabric environments and click on 1 org local fabric to start your local fabric network

## Step 5. (If first time set up or making changes to the smart contract) import, install, and instantiate smart contract 
- On mac open the command palette(shift + common + p)
- Once the command palette is open choose IBM Blockchain Platform: Import a Package. From here select the contract directory from the project (evote/contract) and then choose the contract, in our case voterContract@7.0.0.cds

## Step 6. (If first time set up) export connection details
- Open ibm bc vscode extension under fabric gateways and click on 1 org gateway to connect with the gateway using the admin identity
- Once connected as an admin select the three dots next to fabric gateways and from the dropdown choose export connection profile. Save this file to evote/web-app/server/fabric_connection.json

## Step 7. (if first time set up) export local wallet
