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
- 31 documentation pages processed
- 29 unique endpoints documented
- 52+ schema definitions
- 10 functional areas covered

**Covered API Areas:**
- Authentication (OAuth token generation)
- Vaults (list, get details, assets)
- Signatures (create, list, get details, voting)
- Transfers (native asset, token, sign and broadcast)
- Network (io.network transfers, statement, directory)
- Addresses (validate, register, list, manage, HD addresses)
- Balances (native and token balance queries)
- Chains (list supported chains and features)
- Transactions (create from hex)

**Known Limitations:**
- Chain enum values are incomplete (shows "mnee" + note about 70+ additional values)
- Some nested object schemas (like `nativeCurrency`, `rpcUrls`, `blockExplorers`, `features` in chain responses) are defined as generic objects without detailed properties
- Response examples are not included
- Rate limiting and error response details may be incomplete
