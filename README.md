# Table of contents
* Base URL
* Endpoint types
* Constructing the request
* API documentation
# Base URL
* The base URL is: https://bbt-develop.popcoin.co/
# Endpoint types
### Secure common endpoints
All secure endpoints require authentication and use the method POST.
* [POST /api/next/transfer](#get-transfer)
* [POST /api/next/external-transfer](#get-externaltransfer)
### Secure admin endpoints
* [POST /api/rs/admin/next/mint](#get-mint)
* [POST /api/rs/admin/next/burn](#get-burn)
* [POST /api/rs/admin/next/hotwallet/transfer](#get-hotwallettransfer)
* [POST /api/rs/admin/admin-transfer](#get-admintransfer)
* [POST /api/rs/admin/whitelist-transfer](#get-htransfer)


# Constructing the request
### Request headers (GET, POST)
Authentication requires API KEY. Every request to the server must contain the following in the request header:
* X-RS-APIKEY: {API KEY}
# API documentation
Refer to the following for description of each endpoint
### POST /api/common/next/transfer
#### Description:
for transfer to bitkub next account 
#### Request body:
* `to`		**string**		to address(kyc level 4) (require)
* `amount`		**number**		amount token (require)
* `fee`		**number**		amount token (require)
#### Example:
```
{
  "to": "0x7F8B911b2d1D71155b4deA1EBEA77654943Ee12e",
  "amount": 10,
  "fee": 1
}
```
### Response:
```
{
  "queue_id": "6266751afb0c98001c34af55"
}
```
### Response from queue id:
```
{
  "error": 0,
  "result": {
    "contract_address": "0x6d19ebFd4a26d592FF7afd9eD84B510Fb238D14E",
    "contract_name": "POPCOIN",
    "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "to": "0x7F8B911b2d1D71155b4deA1EBEA77654943Ee12e",
    "method": "TRANSFER",
    "status": "SUCCESS",
    "tx_hash": "0x466fd90108baec6702c4b56aba84a986acc2edac58ce723017bb5e2de3959255",
    "tx_url": "https://testnet.bkcscan.com/tx/0x466fd90108baec6702c4b56aba84a986acc2edac58ce723017bb5e2de3959255/token-transfers",
    "block_confirmations": 5,
    "block_number": 3593508,
    "block_hash": "0xa94aeff9e2c81ac17cad20d0592646c7e4cfd0835ba92a601e233c720a179eae",
    "fee": 1,
    "amount": 10,
    "currency": "POP"
  }
}
```
### POST /api/common/next/external-transfer
#### Description:
for transfer to external account 
#### Request body:
* `to`		**string**		to address (require)
* `amount`		**number**		amount token (require)
* `fee`		**number**		fee token (require)
#### Example:
```
{
  "to": "0x78b9e5760ce2d43c62b2224517cae6aa7a2f1835",
  "amount": 10,
  "fee": 1
}
```
### Response:
```
{
  "queue_id": "6266777fde20a4001c3680ac"
}
```
### Response from queue id:
```
{
  "error": 0,
  "result": {
    "contract_address": "0x6d19ebFd4a26d592FF7afd9eD84B510Fb238D14E",
    "contract_name": "POPCOIN",
    "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "to": "0x78b9e5760ce2d43c62b2224517cae6aa7a2f1835",
    "method": "EXTERNAL_TRANSFER",
    "status": "SUCCESS",
    "tx_hash": "0x7d8c452335bdd19a5c3d7b419b5562e3b54dd510f878c6f10354a7656688a59a",
    "tx_url": "https://testnet.bkcscan.com/tx/0x7d8c452335bdd19a5c3d7b419b5562e3b54dd510f878c6f10354a7656688a59a/token-transfers",
    "block_confirmations": 5,
    "block_number": 3593630,
    "block_hash": "0x580e54ceb89005d953575b870fa8675691d6b6dcade012521e85a41d80ecc30e"
  }
}
```
### POST /api/common/next/mint
#### Description:
for mint bitkub next account 
#### Request body:
* `to`		**string**		to address(kyc level 4) (require)
* `amount`		**number**		amount token (require)
#### Example:
```
{
  "to": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
  "amount": 1000
}
```
### Response:
```
{
  "queue_id": "626678fdde20a4001c3680ad"
}
```
### Response from queue id:
```
{
  "error": 0,
  "result": {
    "contract_address": "0x6d19ebFd4a26d592FF7afd9eD84B510Fb238D14E",
    "contract_name": "POPCOIN",
    "from": "0x0000000000000000000000000000000000000000",
    "to": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "method": "MINT",
    "status": "SUCCESS",
    "tx_hash": "0xe4a6b7257ed19ee3ac3208bc5542b84d1f0f3907fa9ef6ea9e1531e5e682dc48",
    "tx_url": "https://testnet.bkcscan.com/tx/0xe4a6b7257ed19ee3ac3208bc5542b84d1f0f3907fa9ef6ea9e1531e5e682dc48/token-transfers",
    "block_confirmations": 5,
    "block_number": 3593706,
    "block_hash": "0x9052c96498d341926d90671b018284afa0c78db2d6bff955bfca98bb75f75a29"
  }
}
```
### POST /api/common/next/burn
#### Description:
for burn bitkub next account 
#### Request body:
* `from`		**string**		from address(kyc level 4) (require)
* `amount`		**number**		amount token (require)
#### Example:
```
{
  "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
  "amount": 10
}
```
### Response:
```
{
  "queue_id": "62667b2cde20a4001c3680ae"
}
```
### Response from queue id:
```
{
  "error": 0,
  "result": {
    "contract_address": "0x6d19ebFd4a26d592FF7afd9eD84B510Fb238D14E",
    "contract_name": "POPCOIN",
    "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "to": "0x0000000000000000000000000000000000000000",
    "method": "BURN",
    "status": "SUCCESS",
    "tx_hash": "0x37338fa77bda7a820d372895f93953db91948f3d1b1593e3246dd0dab248d3a0",
    "tx_url": "https://testnet.bkcscan.com/tx/0x37338fa77bda7a820d372895f93953db91948f3d1b1593e3246dd0dab248d3a0/token-transfers",
    "block_confirmations": 5,
    "block_number": 3593818,
    "block_hash": "0xc0e553f94410660b13c2aa127beef40fcd5b9e2f8579f1def11ca84a617c4156"
  }
}
```
### POST /api/rs/admin/next/hotwallet/transfer
#### Description:
for transfer to bitkub next account from hotwallet address 
#### Request body:
* `to`		**string**		to address(kyc level 4) (require)
* `amount`		**number**		amount token (require)
#### Example:
```
{
  "to": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
  "amount": 10
}
```
### Response:
```
{
  "queue_id": "62667c83de20a4001c3680af"
}
```
### Response from queue id:
```
{
  "error": 0,
  "result": {
    "contract_address": "0x7F8B911b2d1D71155b4deA1EBEA77654943Ee12e",
    "contract_name": "HOTWALLET",
    "from": "0x7F8B911b2d1D71155b4deA1EBEA77654943Ee12e",
    "to": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "method": "TRANSFER",
    "status": "SUCCESS",
    "tx_hash": "0xaa438063cebca7b2155281f3f587ed8c93a937c470f36cd88de5abcfca9a37bd",
    "tx_url": "https://testnet.bkcscan.com/tx/0xaa438063cebca7b2155281f3f587ed8c93a937c470f36cd88de5abcfca9a37bd/token-transfers",
    "block_confirmations": 5,
    "block_number": 3593887,
    "block_hash": "0x2b01293b81c9e559b7ea6ecfb4401b3e96edf8b6b549130c283231c08244a439",
    "amount": 10,
    "currency": "POP"
  }
}
```
### POST /api/rs/admin/whitelist-transfer
#### Description:
for transfer to hotwallet from whitelist address
#### Request body:
* `from`		**string**		from address(kyc level 4) (require)
* `amount`		**number**		amount token (require)
#### Example:
```
{
  "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
  "amount": 100
}
```
### Response:
```
{
  "error": 0,
  "result": {
    "from": "0x474fa09F7b986315f0654576b972E2cbc4BDdA33",
    "to": "0x7F8B911b2d1D71155b4deA1EBEA77654943Ee12e",
    "amount": 100,
    "fee": 0,
    "contract_name": "POPCOIN",
    "currency": "POP",
    "gas_fee": 0.0003498,
    "gas_used": 69960,
    "block_number": 3606695,
    "tx_hash": "0xc2e232fa45ce196b23f639d9c1c0601850efe5a31be6f9ca6678ab625faec80f",
    "tx_url": "https://testnet.bkcscan.com/tx/0xc2e232fa45ce196b23f639d9c1c0601850efe5a31be6f9ca6678ab625faec80f/token-transfers",
    "timestamp": 1650947768,
    "created_time": "2022-04-26T04:36:08.265Z",
    "updated_time": "2022-04-26T04:36:08.265Z",
    "_id": "626776b8fc3a2b001c76aed5"
  }
}
```
