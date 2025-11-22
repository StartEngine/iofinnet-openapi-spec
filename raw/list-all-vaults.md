# List all vaults
GET https://api.iofinnet.com/v1/vaults

Retrieves a paginated list of all vaults accessible to the user.

Each vault represents a secure storage space for managing digital assets and creating signatures.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

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
  - **id** (string, required) - Unique identifier of the vault
  - **name** (string, required) - Display name of the vault
  - **status** (string, required) - Current status of the vault
- **pageInfo** (object, required)
  - **startCursor** (string, required) - Cursor of the first result in the current page
  - **endCursor** (string, required) - Cursor of the last result in the current page
  - **hasNextPage** (boolean, required) - Indicates if there are more results after the current page
  - **hasPreviousPage** (boolean, required) - Indicates if there are more results before the current page

### 401 Default Response

### 403 Default Response
