# Bulk-create HD addresses
POST https://api.iofinnet.com/v1/vaults/{vaultId}/addresses/ecosystem/{ecosystem}/chain/{chain}/hd-addresses/bulk

Creates multiple hierarchical deterministic (HD) addresses for the specified vault and chain.

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
- Show 70 enum values (additional values not listed)

## Body Params
**indexFrom** (integer, required, >= 0)

**indexTo** (integer, required, >= 0)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 HD addresses created

Response body (object):
- **indexFrom** (integer, required, >= 0)
- **indexTo** (integer, required, >= 0)

### 400 Bad request
