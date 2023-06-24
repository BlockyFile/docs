---
sidebar_position: 6
---

# Change Owner of a File on the BlockyFile Blockchain

## Introduction
In this guide, you will learn how to change the owner of a file on the BlockyFile blockchain using Python and the Web3.py library. We will cover the concept of changing ownership, its significance, and provide a practical example of performing the owner change using the provided Python code.

## Understanding Ownership Change
Changing the owner of a file refers to transferring the control and responsibility of a specific file to a different BlockyFile address. Ownership change is a common operation in decentralized applications (DApps) that manage files or assets on the blockchain. By changing the owner, you can transfer the rights and control over the file to another user or contract.

## Prerequisites
Before proceeding, make sure you have the following:

1. Python installed on your system.
2. Web3.py library installed. You can install it using `pip install web3==5.31.4`.

## Code Example
Here is an example of how to change the owner of a file using Python and Web3.py:

```python
from web3 import Web3

# Connect to a local BlockyFile node
w3 = Web3(Web3.HTTPProvider('https://node1.blockyfile.org'))

# The address of the contract
contract_address = "0xE4B93D2b0bDB461Fe1f5A0Dd4ABBe5133F798d19"

# The ABI (Application Binary Interface) of the contract
contract_abi = [
   {
      "inputs":[
         
      ],
      "name":"GetEncode",
      "outputs":[
         {
            "internalType":"string",
            "name":"",
            "type":"string"
         }
      ],
      "stateMutability":"view",
      "type":"function"
   },
   {
      "inputs":[
         
      ],
      "name":"GetFormat",
      "outputs":[
         {
            "internalType":"string",
            "name":"",
            "type":"string"
         }
      ],
      "stateMutability":"view",
      "type":"function"
   },
   {
      "inputs":[
         
      ],
      "name":"GetOwner",
      "outputs":[
         {
            "internalType":"address",
            "name":"",
            "type":"address"
         }
      ],
      "stateMutability":"view",
      "type":"function"
   },
   {
      "inputs":[
         
      ],
      "name":"Get_Size",
      "outputs":[
         {
            "internalType":"uint256",
            "name":"",
            "type":"uint256"
         }
      ],
      "stateMutability":"view",
      "type":"function"
   },
   {
      "inputs":[
         
      ],
      "name":"RemoveAll",
      "outputs":[
         
      ],
      "stateMutability":"nonpayable",
      "type":"function"
   },
   {
      "inputs":[
         {
            "internalType":"address",
            "name":"newowner",
            "type":"address"
         }
      ],
      "name":"SetOwner",
      "outputs":[
         
      ],
      "stateMutability":"nonpayable",
      "type":"function"
   },
   {
      "inputs":[
         
      ],
      "name":"getValueOfabcd",
      "outputs":[
         {
            "internalType":"string",
            "name":"",
            "type":"string"
         }
      ],
      "stateMutability":"view",
      "type":"function"
   }
]

# The address of the current owner of the contract
current_owner_address = "0x1234567890abcdef1234567890abcdef12345678"

# The private key of the current owner
current_owner_private_key = "0xabcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890"

# The address of the new owner
new_owner_address = "0x9876543210fedcba9876543210fedcba98765432"

# Create a contract object
contract = w3.eth.contract(address=contract_address, abi=contract_abi)

# Build the transaction
transaction = contract.functions.SetOwner(new_owner_address).buildTransaction({
    'from': current_owner_address,
    'gas': 2000000,
    'gasPrice': w3.toWei('50', 'gwei'),
    'nonce': w3.eth.getTransactionCount(current_owner_address),
})

# Sign the transaction
signed_transaction = w3.eth.account.sign_transaction(transaction, private_key=current_owner_private_key)

# Send the signed transaction
transaction_hash = w3.eth.send_raw_transaction(signed_transaction.rawTransaction)

# Wait for the transaction to be mined
transaction_receipt = w3.eth.wait_for_transaction_receipt(transaction_hash)

# Check the transaction status
if transaction_receipt['status'] == 1:
    print("Owner change successful")
else:
    print("Owner change failed")
```
## Instructions
Follow these steps to change the owner of a file:

1. Make sure you have Python and Web3.py library installed.
2. Replace the `https://node1.blockyfile.org` URL with the URL of your BlockyFile node.
3. Replace the `0xE4B93D2b0bDB461Fe1f5A0Dd4ABBe5133F798d19` contract address with the address of your contract.
4. Replace the `0x1234567890abcdef1234567890abcdef12345678` current owner address with the address of the current owner.
5. Replace the `0xabcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890` current owner private key with the private key of the current owner.
6. Replace the `0x9876543210fedcba9876543210fedcba98765432` new owner address with the address of the new owner.
7. Run the Python code.
8. Check the output message. If it says "Owner change successful," the transaction was successful.

## Changing Contract Owner using MetaMask and JavaScript

This code demonstrates how to change the owner of a smart contract using MetaMask for transaction signing and user authorization.

# Prerequisites

- MetaMask extension installed in your browser.



```html
<!DOCTYPE html>
<html>
<head>
    <script src="https://cdn.jsdelivr.net/npm/web3@1.5.2/dist/web3.min.js"></script>
    <script>
        // Check if MetaMask is installed
        if (typeof window.BlockyFile !== 'undefined') {
            console.log('MetaMask is installed!');
        } else {
            alert('Please install MetaMask to use this functionality.');
        }

        // Request user's permission to access their MetaMask accounts
        BlockyFile.request({ method: 'eth_requestAccounts' })
            .then(function(accounts) {
                // Connect to the BlockyFile network using MetaMask
                const web3 = new Web3(BlockyFile);

                // The address of the contract
                const contractAddress = "0x732EAee168F7e7Fa993acC0F7732200288415009";

                // The ABI (Application Binary Interface) of the contract
                const contractABI = [
                   {
                      "inputs":[],
                      "name":"GetEncode",
                      "outputs":[
                         {
                            "internalType":"string",
                            "name":"",
                            "type":"string"
                         }
                      ],
                      "stateMutability":"view",
                      "type":"function"
                   },
                   {
                      "inputs":[],
                      "name":"GetFormat",
                      "outputs":[
                         {
                            "internalType":"string",
                            "name":"",
                            "type":"string"
                         }
                      ],
                      "stateMutability":"view",
                      "type":"function"
                   },
                   {
                      "inputs":[],
                      "name":"GetOwner",
                      "outputs":[
                         {
                            "internalType":"address",
                            "name":"",
                            "type":"address"
                         }
                      ],
                      "stateMutability":"view",
                      "type":"function"
                   },
                   {
                      "inputs":[],
                      "name":"Get_Size",
                      "outputs":[
                         {
                            "internalType":"uint256",
                            "name":"",
                            "type":"uint256"
                         }
                      ],
                      "stateMutability":"view",
                      "type":"function"
                   },
                   {
                      "inputs":[],
                      "name":"RemoveAll",
                      "outputs":[],
                      "stateMutability":"nonpayable",
                      "type":"function"
                   },
                   {
                      "inputs":[
                         {
                            "internalType":"address",
                            "name":"newowner",
                            "type":"address"
                         }
                      ],
                      "name":"SetOwner",
                      "outputs":[],
                      "stateMutability":"nonpayable",
                      "type":"function"
                   },
                   {
                      "inputs":[],
                      "name":"getValueOfabcd",
                      "outputs":[
                         {
                            "internalType":"string",
                            "name":"",
                            "type":"string"
                         }
                      ],
                      "stateMutability":"view",
                      "type":"function"
                   }
                ];

                // The address of the current owner of the contract
                const currentOwnerAddress = "0x6d3E3DeaCB80DFDba96D8A9A1e2f3Fa6250E10dB";

                // The address of the new owner
                const newOwnerAddress = "0xc9ED28485eE507F0Cf62f22fe4558133305B5B58";

                // Create a contract object
                const contract = new web3.eth.Contract(contractABI, contractAddress);

                // Build the transaction
                const transaction = contract.methods.SetOwner(newOwnerAddress).send({ from: currentOwnerAddress, gas: 200000, gasPrice: web3.utils.toWei('50', 'gwei') })
                    .on('transactionHash', function(hash) {
                        console.log('Transaction hash:', hash);
                    })
                    .on('receipt', function(receipt) {
                        // Check the transaction status
                        if (receipt.status == true) {
                            console.log("Owner change successful");
                        } else {
                            console.log("Owner change failed");
                        }
                    })
                    .on('error', function(error) {
                        console.error('Transaction error:', error);
                    });
            })
            .catch(function(error) {
                console.error('MetaMask account access denied:', error);
            });
    </script>
</head>
<body>
</body>
</html>
```

Follow these steps to change the owner of a smart contract using MetaMask and JavaScript:

1. Open the HTML file in a web browser that has MetaMask installed.
2. If MetaMask is installed, you will see a message in the browser console confirming its presence.
3. MetaMask will prompt you to grant permission for the website to access your accounts. Approve the request.
4. The JavaScript code will connect to the BlockyFile network through MetaMask and initiate the transaction to change the contract owner.
5. You can monitor the transaction progress in the browser console. If the transaction is successful, you will see the message "Owner change successful." Otherwise, you will see "Owner change failed."

Note: Make sure to replace the `contractAddress`, `contractABI`, `currentOwnerAddress`, and `newOwnerAddress` with the actual values for your contract.

Now you have a working code snippet to change the owner of a smart contract using MetaMask and JavaScript!

## Conclusion
Changing the owner of a file on the BlockyFile blockchain is an important operation when managing decentralized applications. By following this guide and using the provided Python code, you can perform an owner change transaction and transfer the ownership rights of a file to a new address.
