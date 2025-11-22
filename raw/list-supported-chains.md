# List supported chains
GET https://api.iofinnet.com/v1/chains

List supported chains and the supported features

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Query Params
**ecosystem** (string, enum)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

**chain** (string, enum)
- Show 74 enum values

**includeTestnets** (boolean)
- Defaults to false

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 List supported chains

Response body (object):
- **data** (array of objects, required)
  - **id** (number | null, required)
  - **name** (string, required)
  - **alias** (string, required)
  - **ecosystem** (string, enum, required)
    - Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate
  - **nativeCurrency** (object, required)
  - **rpcUrls** (object)
  - **blockExplorers** (object)
  - **features** (object, required)

### 400 Bad request
