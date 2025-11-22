# List registered addresses for a vault
GET https://api.iofinnet.com/v1/vaults/{vaultId}/addresses

Retrieves a paginated list of addresses registered for monitoring in the specified vault.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

## Query Params
**first** (string | null)

**last** (string | null)

**before** (string | null)

**after** (string | null)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 List vault addresses

Response body (object):
- **data** (array of objects, required)
  - **address** (string, required)
  - **chain** (string, required)
  - **vaultId** (string, required)
  - **workspaceId** (string, required)
  - **derivationPath** (string | null)
  - **subscriptionId** (string | null, required)
  - **updatedAt** (date-time, required)
  - **tokens** (array of objects, required)
    - **contractAddress** (string, required)
    - **symbol** (string, required)
    - **decimals** (number)
    - **hidden** (boolean)
- **pageInfo** (object, required)
  - **hasNextPage** (boolean, required)
  - **hasPreviousPage** (boolean, required)
  - **startCursor** (string)
  - **endCursor** (string)

### 400 Bad request
