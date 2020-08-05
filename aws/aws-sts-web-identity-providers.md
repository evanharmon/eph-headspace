## AWS STS WEB IDENTITY FEDERATION

## Summary

Notes on doing web identity federation with AWS and the `sts` service

## Resources

- [Inline Session Policies](https://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRoleWithWebIdentity.html)

## Flow

- User Authenticates with Identity Provider
- User Receives token from IP
- User calls AssumeRoleWithWebIdentityRequest To AWS STS
- User Receives Temporary security credentials (default expiration 1 hour)
- User can access dynamodb

## AWS STS Security Token Service Parts

- Web Identity Token
- App ID of provider
- ARN of role

- AccessKeyID, SecretAccessKey, SessionToken
- Expiration (time limit)
- AssumeRoleID
- SubjectFromWebIdentityToken

## Debugging

#### Check Assume Role In Use By Browser

1. Open network tab, locate `cognito-identity.us-east-1.amazon.aws.com`
   network call
2. From the response body `Credentials` JSON object, export `AccessKeyId`,
   `SecretKey`, and `SessionToken` to a terminal session as `AWS_ACCESS_KEY_ID`,
   `AWS_SECRET_ACCESS_KEY`, and `AWS_SESSION_TOKEN`
3. Run `aws sts get-caller-identity` to see what account id and role is being assumed

```javascript
{
    "UserId": "ABBBBBBBBBBBBBBBBBBBB:CognitoIdentityCredentials",
    "Account": "111111111111",
    "Arn": "arn:aws:sts::111111111111:assumed-role/my-assume-role/CognitoIdentityCredentials"
}
```
