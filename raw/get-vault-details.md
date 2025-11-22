# Get vault details
GET https://api.iofinnet.com/v1/vaults/{vaultId}

Retrieves detailed information about a specific vault by its ID.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault to retrieve

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the vault
- **name** (string, required) - Display name of the vault
- **status** (string, required) - Current status of the vault
- **createdAt** (string, required) - ISO timestamp when the vault was created
- **updatedAt** (string, required) - ISO timestamp when the vault was last updated
- **signers** (array of objects, required)
  - **id** (string, required) - Unique identifier of the signer
  - **weight** (number, required) - Voting weight of the signer
  - **device** (object, required)
    - **curves** (array of objects, required)
      - **algorithm** (string, required) - Algorithm of the curve
      - **curve** (string, required) - Curve of the curve
      - **publicKey** (string, required) - Public key of the curve

### 401 Default Response

### 403 Default Response

### 404 Default Response
