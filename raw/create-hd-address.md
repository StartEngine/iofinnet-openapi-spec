# Create HD address
POST https://api.iofinnet.com/v1/vaults/{vaultId}/addresses/ecosystem/{ecosystem}/chain/{chain}/hd-addresses

Creates a hierarchical deterministic (HD) for the specified vault and chain.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**ecosystem** (string, enum, required)
- Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

**chain** (string, enum, required)
- abstract
- Show 74 enum values (additional values not listed)

## Body Params
**derivationPath** (string)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 201 HD address created

Response body (object):
- **address** (string, required)
- **chain** (string, enum, required)
  - Allowed: mnee, ripple, ripple-testnet, bittensor, tron, solana, bitcoin, avalanche-p-chain, avalanche-x-chain, cardano, abstract, arbitrum, arbitrum-nova, astar, avalanche-c, base, berachain, blast, bsc, celo, coqnet, cronos, degen, dfk, dfk-testnet, eth, eth-sepolia, fantom, flame, flow-evm, fluent-devnet, fraxtal, fuse, gnosis, ink, lamina1, lightlink, linea, lukso, manta-pacific, mantle, matchain, metal, metis, mint-sepolia, mode, monad-testnet, moonriver, morph, morph-holesky-testnet, optimism, orderly-network, perennial, plume-devnet, polygon, polygon-zkevm, pulsechain, quai, rari, ronin, scroll, shimmer-evm, sonic, sophon-testnet, superposition-testnet, superseed-sepolia, xai, xdc, zksync-era, zora
- **vaultId** (string, required)
- **derivationPath** (string | null)
- **ecosystem** (string, enum, required)
  - Allowed: cosmos, evm, svm, tvm, utxo, xrp, substrate

### 400 Bad request
