# Create a native asset transfer
POST https://api.iofinnet.com/v1/vaults/{vaultId}/{chainAlias}/transfer/native

Create a native asset transfer and broadcast it to chain

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**chainAlias** (string, enum, required)
- BTC
- Show 15 enum values (additional values not listed)

## Body Params
**amount** (string, required)

**receivingAddress** (string, required)

**memo** (string | null)
A free-form text field for additional information

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
