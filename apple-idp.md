# APPLE IDP

## Summary

Notes on developing with apple's third-party auth service

## Resources

- [Getting Started](https://developer.apple.com/sign-in-with-apple/get-started/)
- [AuthenticationServices](https://developer.apple.com/documentation/authenticationservices)
- [Web Sign In With Apple JS](https://developer.apple.com/documentation/signinwithapplejs)
- [AWS Cognito Setup](https://aws.amazon.com/blogs/security/how-to-set-up-sign-in-with-apple-for-amazon-cognito/)
- [Capabilities By Account Type](https://help.apple.com/developer-account/#/dev21218dfd6)
- [Displaying Sign In With Apple](https://developer.apple.com/documentation/sign_in_with_apple/sign_in_with_apple_js/displaying_sign_in_with_apple_buttons)

### Manage Apps Using Apple ID

visit `https://appleid.apple.com/#!&page=signin`

Security section, `APPS & WEBSITES USING APPLE ID`, click `Manage`

### Scopes

Scopes and attributes only shared on initial sign up

- [AWS Cognito Docs](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-social-idp.html#cognito-user-pools-social-idp-step-2)

### Enterprise Apple Accounts

NOT SUPPORTED

### Testing

Allow ios Device / mac to display allow / 2FA code

- use mac signed in with same apple id
- use phone signed in with same apple id
