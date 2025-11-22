# Get token balances for an address
GET https://api.iofinnet.com/v1/balances/ecosystem/{ecosystem}/chain/{chain}/address/{address}/tokens

Get all token balances (ERC-20, SPL, etc.) for a specific address

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

### 200 Token balances retrieved successfully

Response body (object):
- **data** (array of objects, required)
  - **balance** (string, required)
  - **symbol** (string, required)
  - **decimals** (number, required)
  - **address** (string, required)
  - **name** (string | null, required)
  - **logo** (string | null, required)
  - **usdValue** (string | null, required)

### 400 Bad request
