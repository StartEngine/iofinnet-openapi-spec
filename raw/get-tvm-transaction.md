# Get transaction
GET https://api.iofinnet.com/v1/transactions/ecosystem/tvm/chain/{chain}/address/{address}/transaction/{transactionHash}

Retrieves a transaction associated with a specific address on tvm ecosystem

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- Allowed: tron

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
  - Allowed: tron
- **accountAddress** (string, required)
- **classificationData** (object, required)
  - **description** (string, required)
  - **transfers** (array of objects, required)
    - **action** (string, required)
    - **from** (object, required)
    - **to** (object, required)
    - **amount** (string, required)
    - **token** (object, required)
- **rawTransactionData** (object, required)
  - **transactionHash** (string, required)
  - **fromAddress** (string, required)
  - **toAddress** (string, required)
  - **blockNumber** (number, required)
  - **gas** (number, required)
  - **gasUsed** (number, required)
  - **gasPrice** (number, required)
  - **transactionFee** (object, required)
  - **timestamp** (number, required)
  - **operationId** (string, required)

### 404 Transaction not found

### 500 Internal server error
