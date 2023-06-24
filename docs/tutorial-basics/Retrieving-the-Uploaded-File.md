---
sidebar_position: 5
---

# Retrieving the Uploaded File

Once you have uploaded a file to BlockyFile, you can easily retrieve its contents by calling the `GetData` function. This function allows you to retrieve the original file data associated with a specific smart contract address.

To make this process even more convenient, we provide code examples in both Python and JavaScript to demonstrate how you can retrieve the file using the BlockyFile API.

### Python Example

To retrieve the file data in Python, you can use the following code snippet:

```python
from web3 import Web3

# Connect to a local BlockyFile node
w3 = Web3(Web3.HTTPProvider('https://node1.blockyfile.org'))

contract_address = input("Enter the contract address to extract data (e.g., 0xE4B93D2b0bDB461Fe1f5A0Dd4ABBe5133F798d19): ")

# Convert the contract address to a checksum address
contract_address = Web3.toChecksumAddress(contract_address)

# The ABI (Application Binary Interface) of the contract
contract_abi = [
    {
        "inputs": [],
        "name": "GetData",
        "outputs": [
            {
                "internalType": "string",
                "name": "",
                "type": "string"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    }
]

# Create a contract object
contract = w3.eth.contract(address=contract_address, abi=contract_abi)

# Call the function
result = contract.functions.GetData().call()

# Print or process the retrieved file data as needed
print(result)

# You can store the data in a file
with open("data.txt", "w") as file:
    file.write(result)

```

Make sure to replace the placeholder `contractAddress` with the actual smart contract address from which you want to retrieve the data. The code will connect to the BlockyFile node, create a contract object, and call the `GetData` function to retrieve the file data. The retrieved data can be printed or processed further according to your requirements.

### JavaScript Example

If you prefer to use JavaScript, here's an example of how you can retrieve the file data using the Web3 library:

```javascript
const Web3 = require('web3');

// Connect to a local BlockyFile node
const web3 = new Web3('https://node1.blockyfile.org');

const contractAddress = prompt("Enter the contract address to extract data (e.g., 0xE4B93D2b0bDB461Fe1f5A0Dd4ABBe5133F798d19): ");

// The ABI (Application Binary Interface) of the contract
const contractABI = [
    {
        "inputs": [],
        "name": "GetData",
        "outputs": [
            {
                "internalType": "string",
                "name": "",
                "type": "string"
            }
        ],
        "stateMutability": "view",
        "type": "function"
    }
];

// Create a contract object
const contract = new web3.eth.Contract(contractABI, contractAddress);

// Call the function
contract.methods.GetData().call()
    .then(result => {
        // Print or process the retrieved file data as needed
        console.log(result);

        // You can store the data in a file
        const fs = require('fs');
        fs.writeFileSync("data.txt", result);
    });
```
Similarly, replace the placeholder contractAddress with the actual smart contract address and run the code to retrieve the file data.

By utilizing these code examples, you can easily retrieve the uploaded file data from BlockyFile using the GetData function in either Python or JavaScript, enabling you to process, display, or store the data as required.

Next, we will explore more advanced features and functionalities of BlockyFile. Continue reading the following sections for more details.
