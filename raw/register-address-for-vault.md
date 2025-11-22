# Register address for vault
POST https://api.iofinnet.com/v1/vaults/{vaultId}/addresses/ecosystem/{ecosystem}/chain/{chain}

Register address to vault. This will start monitoring the address if monitoring is supported for the chain.

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
**address** (string, required)

**derivationPath** (string | null)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 Address record created

Response body (object):
- **address** (string, required)
- **derivationPath** (string | null)

### 400 Bad request
