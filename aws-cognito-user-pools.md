# AWS COGNITO USER POOLS

## Summary

Notes on setup and use of oauth2 federated third party login providers such as
facebook, google, and amazon

## Resources

[Amplify Oauth2 Setup](https://aws-amplify.github.io/docs/js/cognito-hosted-ui-federated-identity#facebook-instructions)
[Amplify Code Example](https://aws-amplify.github.io/docs/js/authentication)
[AWS Facebook Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-configuring-federation-with-social-idp.html)
[OAuth 2.0 Grants](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)
[RCBJ Blog Tutorial](https://medium.com/@robert.broeckelmann/openid-connect-authorization-code-flow-with-aws-cognito-246997abd11a)
[Chris Concannon Three Legged OAuth Blog](https://blogby.cc/tech-talk/oauth2-lambda/)
[List Of Cognito Trigger Sources For Lambda](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html#cognito-user-identity-pools-working-with-aws-lambda-trigger-sources)

## Scopes

The phone, email, and profile scopes can only be requested if openid is also requested.

## Implicit Grant

Only use the implicit grant when there’s a specific reason that the
authorization code grant can’t be used. This exposes the user pool tokens.

However, if your setup doesn’t contain any server-side logic, you may want to
use the implicit grant to prevent refresh tokens from being exposed to the
client, as the implicit grant does not generate refresh tokens.

## Grant Types

[AWS Blog](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)

#### Authorization Code Grant

Benefit is that user pool token is never shared with end user.

#### Implicit Grant

- Does not generate refresh tokens.
- This is the preferred method for security on
  Single-Page Applications (SPA) which reveal the Client Secret.

## Configuration Pages

[OpenID Configuration](https://cognito-idp.us-east-1.amazonaws.com/us-east-1_aaaaaaaaa/.well-known/openid-configuration)
[JWKS Configuration](https://cognito-idp.us-east-1.amazonaws.com/us-east-1_aaaaaaaaa/.well-known/jwks.json)

## Triggers

### Lambda Invokation From Cognito Policy

in terraform:

```
resource "aws_lambda_permission" "allow_invocation_from_cognito" {
  provider      = aws.cross-account
  statement_id  = "AllowExecutionFromCognito"
  action        = "lambda:InvokeFunction"
  function_name = module.post_confirmation_trigger.lambda_name
  principal     = "cognito-idp.amazonaws.com"
  source_arn    = module.cognito_user_pool.user_pool.arn
}
```
