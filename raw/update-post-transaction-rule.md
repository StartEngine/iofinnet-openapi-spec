# Update a post transaction rule
PUT https://api.iofinnet.com/v1/vaults/{vaultId}/rules/{ruleId}

Update a post transaction rule

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Path Params
**vaultId** (string, required)

**ruleId** (string, required)

## Body Params
**rule** (object, required)

## Headers
**Authorization** (string, required)
Include a Bearer token in the 'Authorization' header. For example: 'Bearer YOUR_TOKEN_HERE'

## Responses

### 200 Post transaction rule updated

Response body (object):
- **config** (required)

### 400 Bad request

### 404 Not found

### 500 Internal server error
