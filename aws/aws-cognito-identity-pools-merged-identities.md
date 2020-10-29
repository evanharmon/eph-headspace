# AWS COGNITO IDENTITY POOL MERGED IDENTITIES

## Summary

Notes on dealing with merge identities in a cognito identity pool

## Resources

- [AWS Forum Answer Disabled Logins](https://forums.aws.amazon.com/thread.jspa?threadID=238042)
- [Switching Identities](https://docs.aws.amazon.com/cognito/latest/developerguide/switching-identities.html)

## Disabled Identity Id

On future calls, GetCredentialsForIdentity, GetId, GetOpenIdToken, GetOpenIdTokenForDeveloperIdentity will all return the non-disabled identity ID.
