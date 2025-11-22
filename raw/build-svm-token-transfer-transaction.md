# Build token transfer transaction hex
POST https://api.iofinnet.com/v1/vaults/{vaultId}/transactions/ecosystem/svm/chain/solana/build-token-transaction

Builds a transaction hex for a token transfer on chain.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

## Body Params
**amount** (string, required)

**to** (string, required)

**derivationPath** (string | null)

**tokenAddress** (string, required)

**decimals** (number, required)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 Transaction hex built

Response body (object):
- **serializedTransaction** (array of strings, required)
- **marshalledHex** (string, required)

### 400 Bad request
