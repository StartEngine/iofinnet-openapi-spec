# Authentication
Securing your integrations with IO's OAuth authentication system

Ensuring the security of our API is of utmost importance. At IO, we employ OAuth authentication protocols to guard against unauthorized access and to fortify the integrity of your financial activities. Note that io.vault and io.network users will still be protected by our cutting edge MPC TSS cryptography, when interacting with these products, our API is purely for orchestration purposes and signatures still need to be produced by the MPC TSS cryptographic process.

## Generating Credentials
To initiate the process, sign in to your IO account. Proceed to the 'Account' then 'API Keys' section to generate a new client ID and client secret. This pivotal step allows for the option to confine access to specified IP addresses, enhancing security measures. Should the necessity arise, these keys can be promptly deleted, thereby revoking access forthwith.

## Key Management Best Practices
Regular rotation of your keys is a security best practice that we highly recommend. Configure IP restrictions to align with trusted devices that are equipped with robust security measures. These proactive actions are critical in safeguarding your financial transactions.

## Secure Transmission
Our platform strictly requires HTTPS for all authentication processes. Any attempt to connect via HTTP will be automatically denied, ensuring that data transmissions adhere to the highest security standards.

## Confidentiality of Keys
Your client ID and client secret are akin to the keys to a vault and should be treated with the highest level of confidentiality. They must never be shared and should be securely stored to prevent any unauthorized access.

## Implementing Authentication
Incorporate the authentication tokens into your system requests as shown in the example below. Remember to replace, <client_id> and <client_secret> with your secrets to ensure authenticated access to the platform.

### Fetching an Access Token
JavaScript

```javascript
const authResponse = await fetch('https://api.iofinnet.com/v1/auth/accessToken', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Accept: 'application/json'
  },
  body: JSON.stringify({
    clientId: "<client_id>",
    clientSecret: "<client_secret>"
  })
});
```

### Authenticated Example
JavaScript

```javascript
const vaults = await fetch('https://api.iofinnet.com/v1/vaults', {
    method: 'GET',
    headers: {
        'Content-Type': 'application/json',
        Accept: 'application/json',
        Authorization: `Bearer ${authResponse.accessToken}`
    }
});
```
