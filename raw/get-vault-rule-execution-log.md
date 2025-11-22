# Get a vault rule execution log
GET https://api.iofinnet.com/v1/vaults/{vaultId}/rules/executions/{executionLogId}

Get a vault rule execution log

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**executionLogId** (string, required)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Vault rule execution log

Response body (object):
- **data** (object, required)
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

### 404 Vault rule execution log not found

### 500 Internal server error
