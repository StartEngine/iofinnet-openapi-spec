# Scan EVM transaction for security threats
POST https://api.iofinnet.com/v1/transactions/ecosystem/evm/chain/{chain}/scan-transaction

Scans an EVM transaction for potential security threats using Blockaid.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**chain** (string, enum, required)
- abstract
- Show 60 enum values

## Body Params
**options** (array of strings, length ≥ 1)
- Defaults to validation
- List of one or more options for the desired output:
  - 'simulation' - include simulation output in your response
  - 'validation' - include security validation of the transaction in your response
  - 'gas_estimation' - include gas estimation result in your response
  - 'events' - include event output in your response
- Default is ['validation']

**metadata** (object, required)
- **block** (string | integer | string)
  - Defaults to 'latest'
  - The relative block for the block validation. Can be 'latest' or a block number or a block hash (hex string starting with 0x)
- **simulate_with_estimated_gas** (boolean)
  - Defaults to false
  - Simulate transaction using gas estimation result. This requires the 'gas_estimation' option to be enabled

**account_address** (string, required)
- The address to relate the transaction to. Account address determines in which perspective the transaction is simulated and validated

**data** (object, required)
- Transaction data object

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 EVM transaction scan completed

Response body (object):
- **result** (object, required)
  - **action** (string, required) - The action Blockaid determined for the transaction
  - **reason** (string) - Reason for the action, if any
  - **details** (object) - Details about the scan result
    - **simulation** (object) - Simulation result for EVM transaction
      - **error** (string) - Error message if simulation failed
      - **balanceChanges** (array of objects) - List of balance changes for involved addresses
        - **address** (string, required) - Address whose balance changed
        - **before** (string, required) - Balance before the transaction
        - **after** (string, required) - Balance after the transaction
      - **gasUsed** (string) - Gas used in the simulation
      - **gasLimit** (string) - Gas limit for the transaction
      - **gasPrice** (string) - Gas price used in the simulation
      - **fee** (string) - Transaction fee calculated in the simulation

### 400 Bad request
