# Get network transfer details
GET https://api.iofinnet.com/v1/vaults/{vaultId}/network/transfers/{transferId}

Retrieves detailed information about a specific network transfer.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault

**transferId** (string, required)
Unique identifier of the transfer

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the transfer request
- **signatureId** (string, required) - Unique identifier of the signature request
- **transactionHash** (string | null, required) - Hash of the on-chain transaction
- **status** (string, enum, required) - Current status of the transfer
  - Allowed: PENDING, VOTING, BROADCASTING, PRESIGNING, SIGNING, SUBMITTED, COMPLETED, REJECTED, CANCELLED, FAILED, EXPIRED, CONTRACT_FAILED
- **amount** (string, required) - Amount to transfer
- **fromAddress** (string, required) - Address sending the assets
- **toAddress** (string, required) - Address to receive the assets
- **memo** (string | null) - Freeform memo or description
- **asset** (object, required)
  - **id** (string, required) - Unique identifier of the asset
  - **name** (string, required) - Display name of the asset
  - **symbol** (string, required) - Symbol of the asset
- **createdAt** (string, required) - ISO timestamp when the request was created
- **updatedAt** (string, required) - ISO timestamp when the request was last updated
- **expiresAt** (string | null) - ISO timestamp when the request expires

### 401 Default Response

### 403 Default Response

### 404 Default Response
