# List transactions
GET https://api.iofinnet.com/v1/transactions/ecosystem/utxo/chain/{chain}/address/{address}

Retrieves a paginated list of transactions associated with a specific address on utxo ecosystem

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- Allowed: mnee, mnee-testnet, bitcoin, litecoin, cardano, avalanche-p-chain, avalanche-x-chain

**address** (string, required)

## Query Params
**first** (string)
- The number of transactions to return - 1 to 50 - Default is 15

**after** (string | null)
- The cursor to begin querying from

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 List of transactions with pagination details

Response body (object):
- **data** (array of objects, required)
  - **chain** (string, enum, required)
    - Allowed: mnee, mnee-testnet, bitcoin, litecoin, cardano, avalanche-p-chain, avalanche-x-chain
  - **accountAddress** (string, required)
  - **classificationData** (object, required)
  - **transfers** (array of objects, required)
    - **action** (string, required)
    - **from** (object, required)
    - **to** (object, required)
    - **amount** (string, required)
    - **token** (object)
    - **nft** (object)
  - **rawTransactionData** (object, required)
- **pagination** (object, required)
  - **hasNextPage** (boolean, required)
  - **hasPreviousPage** (boolean, required)
  - **nextCursor** (string | null, required)
  - **previousCursor** (string | null, required)

### 500 Internal server error
