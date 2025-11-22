# Validate address
POST https://api.iofinnet.com/v1/addresses/ecosystem/{ecosystem}/chain/{chain}/validate

Validates an address against a chain and ecosystem.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**ecosystem** (string, enum, required)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

**chain** (string, enum, required)
- mnee
- Show 70 enum values (additional values not listed)

## Body Params
**address** (string, required)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Address validated

Response body (object):
- **address** (string, required)
- **valid** (boolean, required)

### 400 Bad request
