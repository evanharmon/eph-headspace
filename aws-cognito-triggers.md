# AWS COGNITO TRIGGERS

## Summary

Notes on working with triggers on cognito user pools

## Resources

- [Docs](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html)

### Lambdas Considerations

- all triggered lambdas must return within 5 seconds
- all error messages from Lambdas are visible on AWS Cognito Hosted UI as query
  params
