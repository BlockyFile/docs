---
sidebar_position: 2
---

# Hosting the BlockyFile API Server

This guide will walk you through the steps to download and host the BlockyFile API server using the uploader file.

## Prerequisites

- Python Python 3.x (up to version 3.9) installed on your system

## 1. Download the File Uploader

1. To download the BFY Data Uploader program, you can use the following command:

```shell
git clone https://github.com/BlockyFile/BFY-Data-Uploader.git
```

Alternatively, you can download the program from the [official GitHub download page](https://github.com/BlockyFile/BFY-Data-Uploader/).


## 2. Access the Tools Directory

1. Navigate to the extracted BlockyFile File Uploader folder.
2. Open the "tools" directory.

## 3. Start the API Server

1. Locate the "api.py" file in the "tools" directory.
2. Open a command prompt or terminal and navigate to the directory where "api.py" is located.
3. Execute the following command to start the API server:

```bash
  python api.py
```


# Hosting the BlockyFile API Server

The server will start running on port 5005.

## Accessing the API Server

Once the API server is running, you can access it using the following URL:


`http://localhost:5005/`


You can now make API requests to the BlockyFile server for various operations.

## Additional Configuration


Note: If you want to change the server port, open the "api.py" file in a text editor and locate the line `app.run(host='0.0.0.0', port=5005)`. Change the port value to your desired port number.