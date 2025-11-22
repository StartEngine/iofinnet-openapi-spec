# Update address
PATCH https://api.iofinnet.com/v1/vaults/{vaultId}/addresses/ecosystem/{ecosystem}/chain/{chain}/address/{address}

Updates the hidden assets for registered address

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**ecosystem** (string, enum, required)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

**chain** (string, enum, required)
- abstract
- Show 74 enum values

**address** (string, required)

## Body Params
**addToHiddenAssets** (array of strings)

**removeFromHiddenAssets** (array of strings)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 Address updated

Response body (object):
- **addToHiddenAssets** (array of strings)
- **removeFromHiddenAssets** (array of strings)

### 400 Bad request
