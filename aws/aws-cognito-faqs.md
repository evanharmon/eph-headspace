# AWS COGNITO FAQS

## Summary

Frequently asked questions for Cognito

## Resources

- [FAQs](https://aws.amazon.com/cognito/faqs/)

### Cognito Identity IDs

#### Are Authenticated Identity IDs Unique?

```
For Authenticated Identities (those logging in with a login provider such as Facebook or an OpenID Connect provider), each call to Cognito Identity’s GetId API will only ever create a single identity for each user.
```

### Cognito User Pool Subs

#### Mapping to Identity IDs

Have to manage it yourself in a mapping table

- [Map User Pool to Cognito Identity Fiasco](https://github.com/aws-amplify/amplify-js/issues/54)
- [Mapping](https://serverless-stack.com/chapters/mapping-cognito-identity-id-and-user-pool-id.html)
