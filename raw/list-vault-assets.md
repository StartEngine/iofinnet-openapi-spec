# List vault assets
GET https://api.iofinnet.com/v1/vaults/{vaultId}/assets

Retrieves a list of all assets visible in a specific vault, including their balances and receiving addresses.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required, length ≥ 1)
Unique identifier of the vault

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **data** (array of objects, required)
  - **id** (string, required) - Unique identifier of the asset
  - **publicKey** (string, required) - Public key address for receiving the asset
  - **name** (string, required) - Display name of the asset
  - **symbol** (string, required) - Trading symbol of the asset
  - **contractAddress** (string | null, required) - Contract address of the asset. For native assets, this will be the native token symbol (e.g., "ETH" for Ethereum). For ERC20/TRC20 tokens, this will be the actual contract address.
  - **balance** (string, required) - Current balance of the asset in the vault

### 401 Default Response

### 403 Default Response

### 404 Default Response
