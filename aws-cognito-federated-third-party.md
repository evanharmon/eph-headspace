# AWS COGNITO FEDERATED THIRD PARTY

## Summary

Notes on setup and use of oauth2 federated third party login providers such as
facebook, google, and amazon

## Resources

- [Amplify Oauth2 Setup](https://aws-amplify.github.io/docs/js/cognito-hosted-ui-federated-identity#facebook-instructions)
- [Amplify Code Example](https://aws-amplify.github.io/docs/js/authentication)
- [AWS Facebook Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-configuring-federation-with-social-idp.html)
- [OAuth 2.0 Grants](https://aws.amazon.com/blogs/mobile/understanding-amazon-cognito-user-pool-oauth-2-0-grants/)
- [Apple Id Setup](https://aws.amazon.com/blogs/security/how-to-set-up-sign-in-with-apple-for-amazon-cognito/)

## Facebook

#### Facebook Developer Account Setup

- Create / Login Facebook Account
- Enable developer account at [Developer Page](https://developers.facebook.com)
- Create App
- Under `Settings, Basic` add platform at bottom of page, such as web app

#### Cognito User Pool Setup

- `Federation, Identity Providers` add facebook as an idp. Enter `app id` and
  `app secret` from facebook app page settings. Click
  `Configure attribute mapping` to set email / id mapping

- `App Integration` section, add domain such as `my-awesome-app-dev`
- `App Integration, App client settings` check facebook, set callback url and
  signout url to `http://localhost:3000`. Check the box `Authorization code grant` under
  `Allowed OAuth Flows`. Check the boxes `email` and `openid` under the
  `Allowed OAuth Scopes` section.

#### Facebook App Cognito Settings

- `Settings, Basic` add cognito domain in `site url`. Example
  `https://my-awesome-app-dev.auth.us-east-1.amazoncognito.com/oauth2/idpresponse`

- `Settings, Basic`, at top, add cognito domain to `App Domains` without `oauth2`
  part. Example: `https://my-awesome-app-dev.auth.us-east-1.amazoncognito.com`

- `Products, Settings` add your cognito domain to `Valid Oauth Redirects URIs`.
  Example: `https://my-awesome-app-dev.auth.us-east-1.amazoncognito.com/oauth2/idpresponse`.
  Save Changes.

#### Test Cognito Oauth2 Setup

In a web browser, visit
`https://my-awesome-app-dev.auth.us-east-1.amazoncognito.com/login?response_type=code&client_id=aaaaaaaa11111111111111111&redirect_uri=http://localhost:3000`

## Google

#### Google Developer Console Setup

API & Services, Credentials section:

- Create Project
- Configure OAuth Consent Screen

#### OAuth Consent Screen

- add cognito user pool domain id to `Authorized Domains` and PRESS ENTER

#### Create OAuth Credentials

- in dropdown, choose `OAuth client ID`, choose web application

In form:

- select `web application`
- name of application
- `Authorized Javascript Origins` add user pool domain. This can be found in the
  Cognito, User Pools, App integration, Domain name section of the amazon web
  console
- `Authorized redirect URIs` will be your user pool domain with
  `oauth2/idpresponse` added to the path

#### Cognito Setup

Make sure Cognito setup above in `facebook` section is complete. Go in to
`User Pools, Federation, Attribute mapping`, click `Google` tab and set
attributes to capture and associated user pool attributes

Under `App integration, App client settings` turn on Google for
`Enabled Identity Providers`

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

## Refresh Tokens

[AWS](https://forums.aws.amazon.com/thread.jspa?threadID=241503)

Refresh tokens DO NOT auto refresh when app gets new limited time credentials.
Refresh tokens cannot be refreshed manually.
There is no way to invalidate refresh tokens!
