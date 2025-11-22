# Build token transfer transaction hex
POST https://api.iofinnet.com/v1/vaults/{vaultId}/transactions/ecosystem/evm/chain/{chain}/build-token-transaction

Builds a transaction hex for a token transfer on chain.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**chain** (string, enum, required)
- abstract
- Show 60 enum values

## Body Params
**amount** (string, required)

**to** (string, required)

**derivationPath** (string | null)

**tokenAddress** (string, required)

**gasPrice** (string | null)

**gasLimit** (string | null)

**data** (string | null)

**nonce** (number | null)

**type** (string | null, enum)
- Allowed: legacy, eip1559

**maxFeePerGas** (string | null)

**maxPriorityFeePerGas** (string | null)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 Transaction hex built

Response body (object):
- **serializedTransaction** (array of strings, required)
- **marshalledHex** (string, required)

### 400 Bad request
