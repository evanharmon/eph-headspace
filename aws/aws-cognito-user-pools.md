# AWS COGNITO USER POOLS

## Summary

Notes on setup and use of oauth2 federated third party login providers such as
facebook, google, and amazon

## Resources

- [Amplify Oauth2 Setup](https://aws-amplify.github.io/docs/js/cognito-hosted-ui-federated-identity#facebook-instructions)
- [Amplify Code Example](https://aws-amplify.github.io/docs/js/authentication)
- [AWS Facebook Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-configuring-federation-with-social-idp.html)
- [AWS Identity Provider Api Call Info](https://docs.aws.amazon.com/cognito-user-identity-pools/latest/APIReference/API_CreateIdentityProvider.html#CognitoUserPools-CreateIdentityProvider-request-AttributeMapping)
- [OAuth 2.0 Grants](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)
- [RCBJ Blog Tutorial](https://medium.com/@robert.broeckelmann/openid-connect-authorization-code-flow-with-aws-cognito-246997abd11a)
- [Chris Concannon Three Legged OAuth Blog](https://blogby.cc/tech-talk/oauth2-lambda/)
- [List Of Cognito Trigger Sources For Lambda](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html#cognito-user-identity-pools-working-with-aws-lambda-trigger-sources)
- [Facebook Example](https://www.integralist.co.uk/posts/cognito/)
- [User Pool Auth Flow](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-authentication-flow.html)

### Scopes

The phone, email, and profile scopes can only be requested if openid is also requested.

### Implicit Grant

Only use the implicit grant when there’s a specific reason that the
authorization code grant can’t be used. This exposes the user pool tokens.

However, if your setup doesn’t contain any server-side logic, you may want to
use the implicit grant to prevent refresh tokens from being exposed to the
client, as the implicit grant does not generate refresh tokens.

### Grant Types

- [AWS Blog](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)

#### Authorization Code Grant

Benefit is that user pool token is never shared with end user.

#### Implicit Grant

- Does not generate refresh tokens.
- This is the preferred method for security on
  Single-Page Applications (SPA) which reveal the Client Secret.

### Configuration Pages

- [OpenID Configuration](https://cognito-idp.us-east-1.amazonaws.com/us-east-1_aaaaaaaaa/.well-known/openid-configuration)
- [JWKS Configuration](https://cognito-idp.us-east-1.amazonaws.com/us-east-1_aaaaaaaaa/.well-known/jwks.json)

### Google

#### Typical Identity Provider Details

terraform property example

```hcl
provider_details = {
  attributes_url                = "https://people.googleapis.com/v1/people/me?personFields="
  attributes_url_add_attributes = "true"
  authorize_url                 = "https://accounts.google.com/o/oauth2/v2/auth"
  authorize_scopes              = "profile email openid"
  client_id                     = "myid"
  client_secret                 = "mysecret"
  oidc_issuer                   = "https://accounts.google.com"
  token_request_method          = "POST"
  token_url                     = "https://www.googleapis.com/oauth2/v4/token"
}

attribute_mapping = {
  email    = "email"
  username = "sub"
}
```

### Facebook

#### Common Errors

##### URL blocked Redirect URI is not whitelisted

Don't forget to also change the Valid Oauth Redirect URL in
`Products, Facebook Login, Settings`. The url should end in `/idpresponse`

#### Typical Identity Provider Details

terraform property example

```hcl
provider_details = {
  api_version                   = "v6.0"
  attributes_url                = "https://graph.facebook.com/v6.0/me?fields="
  attributes_url_add_attributes = "true"
  authorize_url                 = "https://www.facebook.com/v6.0/dialog/oauth"
  authorize_scopes              = "public_profile,email"
  client_id                     = "myid"
  client_secret                 = "mysecret"
  oidc_issuer                   = "https://accounts.google.com"
  token_request_method          = "GET"
  token_url                     = "https://graph.facebook.com/v6.0/oauth/access_token"
}

attribute_mapping = {
  email    = "email"
  username = "id"
}
```

### Apple ID

#### Typical Identity Provider Details

terraform property example

```hcl
provider_details = {
  attributes_url_add_attributes = "false"
  authorize_scopes              = "email, name"
  authorize_url                 = "https://appleid.apple.com/auth/authorize"
  client_id                     = "com.mycompany.myapp"
  key_id                        = "mysecret"
  oidc_issuer                   = "https://appleid.apple.com"
  private_key                    = "-----BEGIN PRIVATE KEY----- XXXX -----END PRIVATE KEY-----"
  team_id                       = "AAAAAAAAAA"
  token_request_method          = "POST"
  token_url                     = "https://appleid.apple.com/auth/token"
}

attribute_mapping = {
  email    = "email"
  username = "sub"
}
```
