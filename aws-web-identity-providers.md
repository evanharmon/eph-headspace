# AWS WEB IDENTITY PROVIDERS

## Parts
- Web Identity Token
- App ID of provider
- ARN of role

## Flow
- User Authenticates with Identity Provider
- User Receives token from IP
- User calls AssumeRoleWithWebIdentityRequest To AWS STS
- User Receives Temporary security credentials (default expiration 1 hour)
- User can access dynamodb

## AWS STS Security Token Service Parts
- AccessKeyID, SecretAccessKey, SessionToken
- Expiration (time limit)
- AssumeRoleID
- SubjectFromWebIdentityToken
