# Get registered address
GET https://api.iofinnet.com/v1/vaults/{vaultId}/addresses/ecosystem/{ecosystem}/chain/{chain}/address/{address}

Retrieves details of an address registered for monitoring in the specified vault.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

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

### 200 Get registered address details

Response body (object):
- **data** (array of objects, required)
  - **address** (string, required)
  - **chain** (string, required)
  - **vaultId** (string, required)
  - **workspaceId** (string, required)
  - **derivationPath** (string | null)
  - **subscriptionId** (string | null, required)
  - **updatedAt** (date-time, required)
  - **tokens** (array of objects, required)
    - **contractAddress** (string, required)
    - **symbol** (string, required)
    - **decimals** (number)
    - **hidden** (boolean)

### 400 Bad request
