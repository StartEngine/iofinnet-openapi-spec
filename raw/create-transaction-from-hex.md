# Create transaction from hex
POST https://api.iofinnet.com/v1/vaults/{vaultId}/transactions/ecosystem/{ecosystem}/chain/{chain}/transaction

Creates a transaction record for signing using a pre-built transaction hex, scoped to a specific ecosystem and chain.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**chain** (string, enum, required)
- mnee
- Show 70 enum values

**ecosystem** (string, enum, required)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

## Body Params
**serializedTransaction** (array of strings, required)

**marshalledHex** (string, required)

**memo** (string | null)

**broadcast** (boolean | null)
- Defaults to true

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 Transaction created

Response body (object):
- **id** (string, required)

### 400 Bad request
