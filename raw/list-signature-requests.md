# List signature requests
GET https://api.iofinnet.com/v1/vaults/{vaultId}/signatures

Retrieves a paginated list of all signature requests for a specific vault.

Each signature request represents a pending or completed cryptographic signature operation.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)
Unique identifier of the vault

## Query Params
**limit** (string, defaults to 30)
Maximum number of results to return

**after** (string)
Cursor after which to start returning results

**before** (string)
Cursor before which to start returning results

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **data** (array of objects, required)
  - **id** (string, required) - Unique identifier of the signature request
  - **status** (string, enum, required) - Current status of the signature request (e.g., PENDING, COMPLETED, FAILED)
    - Allowed: PENDING, VOTING, BROADCASTING, PRESIGNING, SIGNING, SUBMITTED, COMPLETED, REJECTED, CANCELLED, FAILED, EXPIRED, CONTRACT_FAILED
  - **memo** (string | null, required) - Optional memo or description of the signature request
  - **errorCode** (string | null, required) - Error code if the request failed
  - **errorMessage** (string | null, required) - Detailed error message if the request failed
  - **createdAt** (string, required) - ISO timestamp when the request was created
  - **updatedAt** (string, required) - ISO timestamp when the request was last updated
  - **expiresAt** (string) - ISO timestamp when the request expires
  - **tags** (array of objects | null, required, defaults to) - Tags associated with the signature request
    - **name** (string, required)
    - **value** (string, required)
    - **mutable** (boolean, required)
    - **isError** (boolean, required)
- **pageInfo** (object, required)
  - **startCursor** (string, required) - Cursor of the first result in the current page
  - **endCursor** (string, required) - Cursor of the last result in the current page
  - **hasNextPage** (boolean, required) - Indicates if there are more results after the current page
  - **hasPreviousPage** (boolean, required) - Indicates if there are more results before the current page

### 401 Default Response

### 403 Default Response

### 404 Default Response
