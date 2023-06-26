---
sidebar_position: 1
---

# BlockyFile Node Installation

To use BlockyFile and participate in the network, you need to install a BlockyFile node on your system. Follow the instructions below carefully to install the node correctly.

## System Requirements

- Processor: Recommended 4/8 cores
- RAM: At least 8/16 GB
- Disk Space: 512 GB

Make sure you meet the minimum system requirements to ensure an optimal experience when using the BlockyFile node.

## Node Installation

1. Download the latest version of Geth from the official GitHub repository. You can find the download link [here](https://github.com/BlockyFile/go-BFY/releases).
2. Once the download is complete, extract the compressed file.
3. Inside the extracted folder, you will also find the `testnet_genesis.json` file.

## Node Initialization

1. Open a terminal or command prompt window.
2. Using the terminal or command prompt, navigate to the directory where you extracted the Geth file.
3. Run the following command to initialize the BlockyFile node:



For Windows:
```bash
geth.exe --datadir "path_to_store_files" init testnet_genesis.json
```
For Linux:
```bash
./geth --datadir "path_to_store_files" init testnet_genesis.json
```
Make sure to replace "path_to_store_files" with the desired location to store the node files.

Next, execute the following command to start the BlockyFile node:

For Windows:
```bash
geth.exe --rpc.gascap 0 --rpc.evmtimeout 120s --miner.gaslimit 220000000 --networkid 171 --datadir path_to_store_files/ --http --http.addr 0.0.0.0 --http.api admin,eth,miner,net,txpool,personal,web3  --http.corsdomain "*" --http.vhosts "*" --http.port 8545 --syncmode full
```
For Linux:
```bash
./geth --rpc.gascap 0 --rpc.evmtimeout 120s --miner.gaslimit 220000000 --networkid 171 --datadir path_to_store_files/ --http --http.addr 0.0.0.0 --http.api admin,eth,miner,net,txpool,personal,web3 --http.corsdomain "*" --http.vhosts "*" --http.port 8545 --syncmode full
```

Customize the command parameters according to your needs. For example, you can modify the IP address, port, and other configuration parameters as desired.

Once you have completed these steps, your BlockyFile node will be successfully installed and ready to use.

## Opening Ports for Geth Service

To ensure proper communication and functionality of the Geth service, you need to open specific ports on your system. Below are the ports that should be opened:

# TCP Port 30303

This is the default port for the Geth P2P protocol. It is used for communication between different nodes in the Ethereum network.

# TCP Port 8545

This port is used for the JSON-RPC API, which allows external applications to interact with the Geth node. It is commonly used for sending requests to the Ethereum network.

# TCP Port 8546

If you want to enable secure communication with TLS/SSL encryption for the JSON-RPC API, you should open this port. It is an optional configuration and not required for regular usage.

# UDP Port 30301

This port is used for the BlockyFile discovery protocol. It helps nodes discover and connect to each other in the network.

Make sure to open these ports in your firewall or network configuration to allow incoming and outgoing traffic for the Geth service.

Note: It's important to apply proper security measures, such as restricting access to trusted IPs or using additional security layers, when opening ports for external communication.

For more information on configuring ports and network settings, please refer to the Geth documentation.



## Advanced Configuration

If you do not want to serve file request queries, you can set the `--rpc.evmtimeout` parameter to 1s.

For additional configuration options and customizations, please refer to the documentation of Geth and BlockyFile.
