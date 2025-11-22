# Create Access Token
POST https://api.iofinnet.com/v1/auth/accessToken

Generate an access token to be used with HTTP Bearer Authentication. See more on Authentication.

## Recent Requests
Log in to see full request history
Time    Status    User Agent
Make a request to see history.

## Body Params
Request Payload

**clientId** (string)
**clientSecret** (string)

## Responses

### 200 OK
Response body (object):
- **accessToken** (string)
- **expiresIn** (integer)
- **type** (string)

### 400 Bad Request

### 401 Unauthorized

### 403 Forbidden

### 5XX Server Error
