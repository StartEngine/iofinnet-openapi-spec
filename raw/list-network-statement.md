# List network statement
GET https://api.iofinnet.com/v1/vaults/{vaultId}/network/statement

Retrieves a paginated list of all io.network transactions for a specific vault.

This endpoint returns a history of all completed io.network transactions, including:

- Transfers between io.network addresses
- Minting and burning operations
- Transaction status and details

Note: This endpoint requires an io.network subscription.

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
  - **id** (string, required) - Unique identifier of the transaction
  - **status** (string, enum, required) - Transaction status (only completed transactions are returned)
    - Allowed: COMPLETED
  - **memo** (string | null, required) - Optional memo given to the transaction
  - **transactionHash** (string, required) - The hash of the transaction on the blockchain
  - **amount** (string, required) - Transaction amount
  - **entryType** (string, enum, required) - Whether the transaction is a debit or credit
    - Allowed: DEBIT, CREDIT
  - **transactionType** (string, enum, required) - Type of transaction
    - Allowed: TRANSFER, MINT, BURN
  - **fromAddress** (string | null, required) - Source address (null for mints)
  - **toAddress** (string | null, required) - Destination address (null for burns)
  - **asset** (object, required)
  - **createdAt** (string, required) - ISO timestamp when the transaction was created
  - **updatedAt** (string, required) - ISO timestamp when the transaction was last updated
- **pageInfo** (object, required)
  - **startCursor** (string, required) - Cursor of the first result in the current page
  - **endCursor** (string, required) - Cursor of the last result in the current page
  - **hasNextPage** (boolean, required) - Indicates if there are more results after the current page
  - **hasPreviousPage** (boolean, required) - Indicates if there are more results before the current page

### 401 Default Response

### 403 Default Response

### 404 Default Response
