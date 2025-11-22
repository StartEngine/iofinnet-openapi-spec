# List asset transactions
GET https://api.iofinnet.com/v1/vaults/{vaultId}/assets/{assetId}/transactions

List asset transactions

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**assetId** (string, required)

## Query Params
**limit** (string, defaults to 30)

**after** (string)

**before** (string)

## Headers
**authorization** (string, required)

## Response

### 200 Default Response

Response body (object):
- **data** (array of objects, required)
  - **id** (string, required)
  - **errorCode** (string | null, required)
  - **errorMessage** (string | null, required)
- **pageInfo** (object, required)
  - **startCursor** (string, required)
  - **endCursor** (string, required)
  - **hasNextPage** (boolean, required)
  - **hasPreviousPage** (boolean, required)
