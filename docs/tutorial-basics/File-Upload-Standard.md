---
sidebar_position: 4
---

# File Upload Standard for Blockchain Smart Contracts

The standard for uploading files to the blockchain requires the smart contract to have the following functionalities:

## GetEncode

The `GetEncode` function returns the encoding type used for the file. For example, if the returned value is "base64", it means that the file has been encoded using Base64 encoding.

## GetFormat

The `GetFormat` function returns the format of the file. For example, if the file is a PNG image, the returned value will be "image".

## GetOwner

The `GetOwner` function returns the address that identifies the owner of the file in the blockchain.

## Get_Size

The `Get_Size` function returns the size of the file in megabytes (MB).

## RemoveAll

The `RemoveAll` function is used to remove all data associated with the file. When this function is called, no data associated with the file will be returned.

## SetOwner

The `SetOwner` function allows changing the owner of the file. This function requires an address as a parameter and verifies that the request comes from the current owner of the file.

## GetData

The `GetData` function returns the file in the format specified by the user. It can return the file in Base64 or in the encoding chosen by the user.

It is important to note that the file upload standard for blockchain may vary depending on the specific contract being used. Make sure to consult the contract's specific documentation for more details and to fully understand the offered functionalities.
