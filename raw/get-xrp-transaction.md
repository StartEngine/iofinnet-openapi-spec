# Get transaction
GET https://api.iofinnet.com/v1/transactions/ecosystem/xrp/chain/{chain}/address/{address}/transaction/{transactionHash}

Retrieves a transaction associated with a specific address on xrp ecosystem

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- Allowed: ripple, ripple-testnet

**address** (string, required)

**transactionHash** (string, required)

## Query Params
**chain** (string, enum, required)
- abstract
- Show 74 enum values

**address** (string, required)

**transactionHash** (string, required)

**ecosystem** (string, enum, required)
- Allowed: evm, svm, utxo, tvm

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Transaction

Response body (object):
- **chain** (string, enum, required)
  - Allowed: ripple, ripple-testnet
- **accountAddress** (string, required)
- **classificationData** (object, required)
  - **type** (string, required)
  - **description** (string, required)
  - **transfers** (array of objects, required)
    - **action** (string, required)
    - **from** (object, required)
    - **to** (object, required)
    - **amount** (string, required)
    - **token** (object, required)
- **rawTransactionData** (object, required)
  - **transactionHash** (string, required)
  - **blockNumber** (number, required)
  - **transactionFee** (object, required)
  - **timestamp** (number, required)
  - **memo** (string)
  - **operationId** (string, required)

### 404 Transaction not found

### 500 Internal server error
