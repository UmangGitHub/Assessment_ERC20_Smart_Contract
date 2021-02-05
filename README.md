# Assessment: ERC20 Smart Contract

Objective: Create an ERC20 smart contract and make two APIs to fetch user balance and transfer tokens using NodeJs.

-------------------------------------------------------------------------------------------------------------------------------------------------------

Solution:

I have created three solidity files:
  1. MyContract.sol
     Implementation of interface ERC20.
  2. SafeMath.sol
     Library to perform addition and subtraction 
  3. ERC20.sol
     Interface ERC20
     
-----------------------

Step by step instructions to deploy smart contract using Remix IDE:

  1. Open the three solidity files in Remix IDE
  2. Run Ganache
  3. In the Deploy & Run Transactions tab of Remix, select the environment to "Web3 Provider". Input Web3 Provider endpoint: "httphttp://127.0.0.1:7545".
  4. In the Deploy & Run Transactions tab of Remix, select "MyContract" ti deploy.
  5. In the "Deploy" input field, enter the total supply of tokens to be given to the samrt contract.Hit the "Deploy" button.

----------------------

Step by step instructions to fetch user balance and transfer tookens using NodeJs:
  1. Open Command Prompt and go to an empty directory
  
  2. Initialize the directory:
     Type in "npm init -y"
  
  3. Install Web3.js
	   Type in “npm install –save web3”
     
  4. Start NodeJS Environment
	   Type in "node"
     
  5. Use web3.js to interact with MyContract
	   Type in:
	   const Web3 = require('web3');
	   const web3 = new Web3(new Web3.providers.HttpProvider('http://localhost:7545'));
     var myContract = new web3.eth.Contract([ABI], "Contract Address");
     
     a.) To fetch user balance:
         myContract.methods.balanceOf("Token_Owner").call().then(console.log);
         
     b.) To transfer tokens:
         myContract.methods.transfer("Receiver_Address", "No_Tokens").send({from: "Sender_Address"}).then(console.log);
