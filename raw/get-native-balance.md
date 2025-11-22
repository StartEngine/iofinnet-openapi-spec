# Get native balance for an address
GET https://api.iofinnet.com/v1/balances/ecosystem/{ecosystem}/chain/{chain}/address/{address}/native

Retrieves the native balance of a specific address on a given chain.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**ecosystem** (string, enum, required)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

**chain** (string, enum, required)
- mnee
- Show 70 enum values

**address** (string, required)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Native balance retrieved successfully

Response body (object):
- **data** (object, required)
  - **balance** (string, required)
  - **symbol** (string, required)
  - **logo** (string | null, required)
  - **name** (string, required)
  - **usdValue** (string | null, required)
  - **lastUpdated** (string, required)

### 400 Bad request
