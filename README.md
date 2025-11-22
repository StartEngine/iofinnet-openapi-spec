# IOFinNet API OpenAPI Specification

## ⚠️ Important Disclaimer

**This is NOT an official IOFinNet specification.** This spec was created on **November 21, 2025** by manually extracting information from the IOFinNet documentation website because no official OpenAPI specification was available at that time.

**Before using this specification:**
1. Check if IOFinNet has published an official OpenAPI spec at https://docs.iofinnet.com or https://iofinnet.com
2. If an official spec is available, use that instead
3. This community-maintained spec may be incomplete or outdated
4. Always verify endpoint behavior against the official IOFinNet documentation

This project was created as a convenience tool and should be used with caution. The maintainers are not affiliated with IOFinNet.

---

## Problem

The IOFinNet documentation site doesn't provide a downloadable OpenAPI spec, making it difficult to:
- Generate client libraries
- Test endpoints systematically
- Integrate with API tools (Postman, Insomnia, etc.)

## Solution

This repository contains:
- **`raw/`** - Raw documentation pages copied from the IOFinNet docs
- **`openapi.json`** - The complete OpenAPI 3.0 specification built from the documentation

## Structure

```
.
├── README.md
├── raw/                    # Raw documentation pages
│   └── *.md               # Each endpoint's documentation
└── openapi.json           # OpenAPI specification
```

## Usage

Once complete, you can:
- Import `openapi.json` into Postman, Insomnia, or other API clients
- Generate client SDKs using tools like `openapi-generator`
- Validate API requests and responses

## Building

The spec is built manually by extracting information from each documentation page and translating it into OpenAPI format.

## Current Status

**Last Updated:** November 21, 2025

**Statistics:**
- 58 documentation pages processed
- 56 unique endpoints documented
- 83 schema definitions
- 11 functional areas covered

**Covered API Areas:**
- **Authentication** - OAuth token generation
- **Vaults** - List, get details, assets, rule execution logs
- **Signatures** - Create, list, get details, voting
- **Transfers** - Native asset, token, sign and broadcast
- **Network** - io.network transfers, statement, directory
- **Addresses** - Validate, register, list, manage, HD addresses, bulk operations
- **Balances** - Native and token balance queries
- **Chains** - List supported chains and features
- **Transactions** - Complete multi-ecosystem support:
  - **EVM** (60+ chains): Get, List, Scan, Build native/token
  - **SVM/Solana**: Get, List, Scan, Build native/token
  - **TVM/Tron**: Get, List, Build native/token
  - **XRP/Ripple**: Get, List, Build native
  - **UTXO** (Bitcoin, Litecoin, Cardano, Avalanche): Get, List, Build native
  - **Substrate** (Bittensor): Build native
- **Rules** - Complete rule lifecycle management:
  - **Rule CRUD**: Create, Read (list/get), Update post-transaction rules
  - **Execution Logs**: List all logs, by rule ID, or get specific log

**Transaction Operations Coverage:**
- ✅ **3 ecosystems with full native + token support**: EVM, SVM, TVM
- ✅ **3 ecosystems with native support**: XRP, UTXO, Substrate
- ✅ **Transaction scanning** (security): EVM, SVM
- ✅ **Transaction history**: EVM, SVM, XRP, UTXO, TVM

**Known Limitations:**
- Chain enum values are incomplete (shows "mnee" + note about 70+ additional values)
- Some nested object schemas (like `nativeCurrency`, `rpcUrls`, `blockExplorers`, `features` in chain responses) are defined as generic objects without detailed properties
- Response examples are not included
- Rate limiting and error response details may be incomplete
- Cosmos ecosystem endpoints not yet documented
