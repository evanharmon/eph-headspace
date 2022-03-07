# SERVERLESS SETUP
## AWS CREDENTIALS
can either be env vars or profiles
```
export AWS_ACCESS_KEY_ID='abcd'
export AWS_SECRET_ACCESS_KEY='xyz'
```

## Set default credentials
`serverless config credentials --provider aws --key abcd --secret xyz`

## Set profile during deploy
`serverless deploy --aws-profile devProfile`

## Invalid Security token
Security Token Included In the Request is Invalid
If you are using MFA - AWS_SESSION_TOKEN env variable is needed
