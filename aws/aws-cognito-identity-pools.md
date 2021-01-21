# AWS COGNITO IDENTITY POOLS

## Summary

Notes on setup and use of oauth2 federated third party login providers such as
facebook, google, and amazon

## Resources

- [Identity Pool Auth Flow](https://docs.aws.amazon.com/cognito/latest/developerguide/authentication-flow.html)
- [Assume Preferred Role](https://docs.aws.amazon.com/cognito/latest/developerguide/role-based-access-control.html)

### Refresh Tokens

- [AWS](https://forums.aws.amazon.com/thread.jspa?threadID=241503)

Refresh tokens DO NOT auto refresh when app gets new limited time credentials.
Refresh tokens cannot be refreshed manually.
There is no way to invalidate refresh tokens!
