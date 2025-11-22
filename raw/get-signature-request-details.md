# Get signature request details
GET https://api.iofinnet.com/v1/vaults/{vaultId}/signatures/{signatureId}

Retrieves detailed information about a specific signature request.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault

**signatureId** (string, required)
Unique identifier of the signature request

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the signature request
- **status** (string, enum, required) - Current status of the signature request
  - Allowed: PENDING, VOTING, BROADCASTING, PRESIGNING, SIGNING, SUBMITTED, COMPLETED, REJECTED, CANCELLED, FAILED, EXPIRED, CONTRACT_FAILED
- **memo** (string | null, required) - Optional memo or description
- **errorCode** (string | null, required) - Error code if the request failed
- **errorMessage** (string | null, required) - Detailed error message if the request failed
- **voting** (object, required)
  - **approvedWeight** (number, required) - Total weight of approved votes
  - **progress** (string, required) - Current voting progress status
  - **threshold** (number, required) - Required weight threshold for approval
  - **votes** (array of objects, required)
    - **required** (boolean, required) - Whether this vote is required
    - **vote** (string | null, enum, required) - Current device vote status. null if device has not voted
      - Allowed: APPROVE, REJECTED
    - **weight** (number, required) - Voting weight of this signer
    - **device** (object, required)
- **signingData** (required)
- **createdAt** (string, required) - ISO timestamp when the request was created
- **updatedAt** (string, required) - ISO timestamp when the request was last updated
- **expiresAt** (string) - ISO timestamp when the request expires
- **tags** (array of objects | null, required, defaults to) - Tags associated with the signature request
  - **name** (string, required)
  - **value** (string, required)
  - **mutable** (boolean, required)
  - **isError** (boolean, required)

### 401 Default Response

### 403 Default Response

### 404 Default Response
