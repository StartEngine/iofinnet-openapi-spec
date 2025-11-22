# List network directory
GET https://api.iofinnet.com/v1/network/directory

Retrieves a paginated list of all entries in the io.network directory.

The directory contains information about registered users and organisations in the io.network ecosystem.

You can search for entries by display name or address.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Query Params
**search** (string)
Search for directory entry by display name or address

**limit** (string, defaults to 30)
Maximum number of results to return

**after** (string)
Cursor after which to start returning results

**before** (string)
Cursor before which to start returning results

## Headers
**authorization** (string, required)
Bearer token for authentication

## Responses

### 200 Default Response

Response body (object):
- **data** (array of objects, required)
  - **id** (string, required) - Unique identifier of the directory entry
  - **address** (string, required) - Blockchain address of the entity
  - **alias** (string, required) - Unique alias/username
  - **type** (string, enum, required) - Type of entity
    - Allowed: INDIVIDUAL, CORPORATE
  - **displayName** (string | null, required) - Display name
  - **companyName** (string | null, required) - Company name (for corporate entities)
  - **legalName** (string | null, required) - Legal name (for corporate entities)

### 401 Default Response

### 403 Default Response
