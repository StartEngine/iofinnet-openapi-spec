# List vault rule execution logs by rule id
GET https://api.iofinnet.com/v1/vaults/{vaultId}/rules/{ruleId}/executions

List vault rule execution logs by rule id

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**ruleId** (string, required)

## Query Params
**first** (string)

**last** (string)

**before** (string)

**after** (string)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 List of rule execution logs for a vault

Response body (object):
- **data** (array of objects, required)
  - **id** (string, required)
  - **rule** (object, required)
  - **status** (string, enum, required)
    - Allowed: started, completed, failed
  - **error** (string | null, required)
  - **errorCause** (string | null, required)
  - **metadata** (string)
  - **executionTimeMS** (string | null, required)
  - **createdAt** (string, required)
  - **updatedAt** (string, required)
- **pageInfo** (object, required)
  - **hasNextPage** (boolean, required)
  - **hasPreviousPage** (boolean, required)
  - **nextCursor** (string | null, required)
  - **previousCursor** (string | null, required)

### 500 Internal server error
