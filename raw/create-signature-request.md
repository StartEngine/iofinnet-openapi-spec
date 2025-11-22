# Create signature request
POST https://api.iofinnet.com/v1/vaults/{vaultId}/signatures/sign

Creates a new signature request for cryptographic signing.

The request will require approval from vault signers based on their configured weights.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault

## Body Params
**data** (string, required)
Unsigned data to be signed (format depends on contentType)

**coseAlgorithm** (string, enum, required)
The COSE algorithm to use for signing
- Allowed: ES256K, ESKEC256, EDDSA

**contentType** (string, enum, required)
The content type of the data
- Allowed: application/octet-stream+hex, application/octet-stream+base64, text/plain, application/x-eip712+json

**source** (string)
Source of the signature request (visible in UI)

**memo** (string | null)
Optional memo or description

**expiresAt** (string | null)
Optional expiration time for the request

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 201 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the signature request
- **signatureId** (string, required) - Unique identifier of the signature request (same as id)
- **status** (string, enum, required) - Current status of the request (PENDING)
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
    - **vote** (string | null, enum, required) - Current vote status. null for new requests
      - Allowed: APPROVE, REJECTED
    - **weight** (number, required) - Voting weight of this signer
    - **device** (object, required)
- **signingData** (object, required)
  - **signature** (string | null, required) - The signature (null for new requests)
  - **data** (string, required) - The unsigned data
  - **contentType** (string, required) - The content type of the data
  - **coseAlgorithm** (object, required)
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

### 422 Default Response
