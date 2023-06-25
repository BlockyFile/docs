---
sidebar_position: 6
---
# Retrieving Uploaded Files on BlockyFile using Public API

BlockyFile provides a public API that allows you to retrieve uploaded files on the platform using the contract address as a parameter. You can use the public API directly from your browser or create your own customized APIs. Below are the steps to retrieve files using the BlockyFile public API.

## Step 1: Obtain the Contract Address

1. Upload your files to the BlockyFile platform using the uploading program or the appropriate user interface.
2. After the upload, the uploading program will provide the contract address associated with the uploaded files.

## Step 2: Retrieving the File in the Original Format (Browser)

1. Use your browser to compose the API request URL in the following format: `https://api.blockyfile.org/v1/?contract_address=<contract_address>`
   For example: `https://api.blockyfile.org/v1/?contract_address=0x123abc...`
2. Open the API URL in your browser.
3. The file will be downloaded in the original format in which it was uploaded to the BlockyFile platform.

## Retrieving the File in JSON Format using curl or wget

To retrieve the file in JSON format using the command line, you can utilize the `curl` or `wget` commands. Follow the steps below:

1. Open your terminal or command prompt.
2. Compose the JSON API request URL in the following format:
   ```
   https://api.blockyfile.org/json/?contract_address=<contract_address>
   ```

   Replace `<contract_address>` with the actual contract address obtained from Step 1.
   For example:

   ```
   https://api.blockyfile.org/json/?contract_address=0x123abc...
   ```

### Using curl

3. Use the `curl` command with the JSON API URL:
   ```bash
   curl -O "https://api.blockyfile.org/json/?contract_address=<contract_address>"
   ```

   Replace `<contract_address>` with the actual contract address obtained from Step 1.

   For example:
   ```bash
   curl -O "https://api.blockyfile.org/json/?contract_address=0x123abc..."
   ```

4. The JSON file will be downloaded to your current directory.

### Using wget

3. Use the `wget` command with the JSON API URL:
   ```bash
   wget "https://api.blockyfile.org/json/?contract_address=<contract_address>"
   ```
   Replace `<contract_address>` with the actual contract address obtained from Step 1.
   For example:
   ```bash
   wget "https://api.blockyfile.org/json/?contract_address=0x123abc..."
   ```

4. The JSON file will be downloaded to your current directory.

By using `curl` or `wget` with the JSON API URL, you can retrieve the file in JSON format containing the file details, including the data encoded in base64 or in a format chosen by the user.

## Using Your Own Customized APIs

1. If you want to use your own customized APIs, you can set up your local server and compose the API request URL as follows: `localhost:8080/v1/?contract_address=<contract_address>`
   For example: `localhost:8080/v1/?contract_address=0x123abc...`
2. Ensure that your local server is up and running, ready to handle the API requests.
3. Open the URL of your customized APIs in your browser or use them within your application or project as required.

Remember to handle access and authentication properly when using the BlockyFile public API or your own customized APIs. Make sure to follow the API guidelines and adhere to the allowed usage policies.
