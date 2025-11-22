# Sign and broadcast a transaction
POST https://api.iofinnet.com/v1/vaults/{vaultId}/{chainAlias}/sign-and-broadcast

Sign and broadcast a transaction

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**chainAlias** (string, enum, required)
- ETH
- Show 13 enum values (additional values not listed)

## Body Params
**receivingAddress** (string, required)

**contractAddress** (string, required)

**contractData** (string, required)

**amount** (string, required)

**memo** (string)

**expiresAt** (date-time | null)

## Headers
**authorization** (string, required)

## Response

### 201 Default Response

Response body (object):
- **id** (string, required)
- **memo** (string, required)
- **createdAt** (string, required)
- **updatedAt** (string, required)
- **expiresAt** (string, required)
