# Create network transfer
POST https://api.iofinnet.com/v1/vaults/{vaultId}/network/transfers

Creates a new transfer request for io.network assets.

Note: This endpoint requires an io.network subscription.

This endpoint initiates a transfer of io.network assets from the vault to a specified address.

The receiving address must be an address that is registered in the io.network directory.

To see the status of the transfer, use the /vaults/:vaultId/network/transfers/:transferId endpoint.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault

## Body Params
**asset** (string, required)
Asset symbol (e.g., IOF)

**amount** (string, required)
Amount to transfer in token units

**toAddress** (string, required)
Address to receive the assets

**memo** (string)
Freeform memo or description

**expiresAt** (string | null)
Optional expiration time for the request

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 201 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the transfer
- **signatureId** (string, required) - Unique identifier of the signature request
- **status** (string, enum, required) - Current status of the transfer
  - Allowed: PENDING, VOTING, BROADCASTING, PRESIGNING, SIGNING, SUBMITTED, COMPLETED, REJECTED, CANCELLED, FAILED, EXPIRED, CONTRACT_FAILED
- **amount** (string, required) - Transfer amount
- **fromAddress** (string, required) - Address sending the assets
- **toAddress** (string, required) - Address to receive the assets
- **memo** (string | null) - Freeform memo or description
- **asset** (string, required) - Asset symbol
- **createdAt** (string, required) - ISO timestamp when the request was created
- **updatedAt** (string, required) - ISO timestamp when the request was last updated
- **expiresAt** (string | null) - ISO timestamp when the request expires

### 401 Default Response

### 403 Default Response

### 404 Default Response

### 422 Default Response
