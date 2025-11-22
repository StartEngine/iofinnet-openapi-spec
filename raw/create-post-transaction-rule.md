# Create a post transaction rule
POST https://api.iofinnet.com/v1/vaults/{vaultId}/rules

Create a post transaction rule

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

## Body Params
**object**

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Post transaction rule created

Response body (object):
- **id** (string, required)
- **type** (string, enum, required)
  - Allowed: auto-sweep
- **friendlyName** (string, required)
- **condition** (string)
- **config** (object, required)
  - **receivingAddressId** (string, required)
- **enabled** (boolean, required)
- **preFundingEnabled** (boolean | null, required)
- **fundingAddressId** (string | null, required)
- **networkFeeMultiplier** (number | null, required)

### 400 Bad request

### 500 Internal server error
