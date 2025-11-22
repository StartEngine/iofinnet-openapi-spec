# Lookup directory entry
GET https://api.iofinnet.com/v1/network/directory/address/{address}

Retrieves detailed information about a specific directory entry by address.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**address** (string, required)
io.network address to look up

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **id** (string, required) - Unique identifier of the directory entry
- **address** (string, required) - io.network address of the entity
- **alias** (string, required) - Unique alias/username
- **type** (string, enum, required) - Type of entity
  - Allowed: INDIVIDUAL, CORPORATE
- **displayName** (string | null, required) - Display name
- **companyName** (string | null, required) - Company name
- **legalName** (string | null, required) - Legal name (for corporate entities)

### 401 Default Response

### 403 Default Response

### 404 Default Response
