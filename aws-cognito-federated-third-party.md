# AWS COGNITO FEDERATED THIRD PARTY

## Summary

Notes on setup and use of oauth2 federated third party login providers such as
facebook, google, and amazon

## Resources

[Amplify Oauth2 Setup](https://aws-amplify.github.io/docs/js/cognito-hosted-ui-federated-identity#facebook-instructions)
[Amplify Code Example](https://aws-amplify.github.io/docs/js/authentication)
[AWS Facebook Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-configuring-federation-with-social-idp.html)

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

#### Test Cognito Setup

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

Make sure Cognito setup above in `faceobok` section is complete. Go in to
`User Pools, Federation, Attribute mapping`, click `Google` tab and set
attributes to capture and associated user pool attributes

Under `App integration, App client settings` turn on Google for
`Enabled Identity Providers`
