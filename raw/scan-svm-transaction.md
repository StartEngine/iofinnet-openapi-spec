# Scan SVM transaction for security threats
POST https://api.iofinnet.com/v1/transactions/ecosystem/svm/chain/{chain}/scan-transaction

Scans an SVM transaction for potential security threats using Blockaid.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- Allowed: solana, solana-testnet

## Body Params
**encoding** (string, enum, required)
- Transaction encoding format
- Allowed: base58 (default), base64

**options** (array of strings, length ≥ 1)
- Defaults to simulation,validation
- List of options to include in the response
- Allowed values: validation, simulation
- Defaults to ["simulation", "validation"]

**account_address** (string, required)
- Solana account address

**transactions** (array of strings, required)
- Transactions to scan

**metadata** (object, required)
- **method** (string)
  - Defaults to signAllTransactions
  - The RPC method used by the dApp to propose the transaction

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 SVM transaction scan completed

Response body (object):
- **encoding** (string, required) - Encoding used for the response
- **status** (string, enum, required) - Status of the simulation/validation
  - Allowed: SUCCESS, ERROR
- **result** (object | null, required) - Result of the request
- **simulation** (object | null, required) - Transaction Simulation Result
- **validation** (object | null, required) - Transaction Validation Result
- **error** (string | null) - Error message if the simulation or validation failed
- **error_details** (object) - Error details
  - **api_error** (object) - API error details
  - **instruction_error** (object) - Instruction error details
  - **transaction_error** (object) - Transaction error details
- **request_id** (string, required) - Unique identifier of the request

### 400 Bad request
