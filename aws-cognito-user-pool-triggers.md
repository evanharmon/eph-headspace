# AWS COGNITO TRIGGERS

## Summary

Notes on working with triggers on cognito user pools

## Resources

- [Docs](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-triggers.html)
- [AWS Examples](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools-working-with-aws-lambda-triggers.html)
- [PostConfirmation](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-lambda-post-confirmation.html)

### Lambdas Considerations

- all triggered lambdas must return within 5 seconds
- all error messages from Lambdas are visible on AWS Cognito Hosted UI as query
  params

### Event Request User Attributes

```javascript
const { email } = event.request.userAttributes
```

### Post Confirmation

Confirmed: if post confirmation trigger lambda errors out, user is still created
in user pool
