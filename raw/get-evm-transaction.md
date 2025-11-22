# Get transaction
GET https://api.iofinnet.com/v1/transactions/ecosystem/evm/chain/{chain}/address/{address}/transaction/{transactionHash}

Retrieves a transaction associated with a specific address on evm ecosystem

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- abstract
- Show 60 enum values

**address** (string, required)

**transactionHash** (string, required)

## Query Params
**chain** (string, enum, required)
- abstract
- Show 74 enum values

**address** (string, required)

**transactionHash** (string, required)

**ecosystem** (string, enum, required)
- Allowed: evm, svm, utxo, tvm

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Transaction

Response body (object):
- **chain** (string, enum, required)
  - Allowed: abstract, arbitrum, arbitrum-nova, astar, avalanche-c, base, berachain, blast, bsc, celo, coqnet, cronos, degen, dfk, dfk-testnet, eth, eth-sepolia, fantom, flame, flow-evm, fluent-devnet, fraxtal, fuse, gnosis, ink, lamina1, lightlink, linea, lukso, manta-pacific, mantle, matchain, metal, metis, mint-sepolia, mode, monad-testnet, moonriver, morph, morph-holesky-testnet, optimism, orderly-network, perennial, plume-devnet, polygon, polygon-zkevm, pulsechain, quai, rari, ronin, scroll, shimmer-evm, sonic, sophon-testnet, superposition-testnet, superseed-sepolia, xai, xdc, zksync-era, zora
- **accountAddress** (string, required)
- **classificationData** (object, required)
  - **type** (string, required)
  - **description** (string, required)
  - **transfers** (array of objects, required)
    - **action** (string, required)
    - **from** (object, required)
    - **to** (object, required)
    - **amount** (string, required)
    - **token** (object)
    - **nft** (object)
- **rawTransactionData** (object, required)
  - **transactionHash** (string, required)
  - **fromAddress** (string, required)
  - **toAddress** (string, required)
  - **blockNumber** (number, required)
  - **gas** (number, required)
  - **gasUsed** (number, required)
  - **gasPrice** (number, required)
  - **transactionFee** (object, required)
  - **timestamp** (number, required)

### 404 Transaction not found

### 500 Internal server error
