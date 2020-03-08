# AWS SDK JAVASCRIPT

## Summary

Notes on working with the javascript aws sdk

## Resources

- [AWS Docs](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/)
- [v4 Sign Docs](https://docs.aws.amazon.com/general/latest/gr/signature-v4-examples.html#signature-v4-examples-javascript)

## Retrieve Credentials

```javscript
const creds = AWS.Config.credentials.get()
```

## V4 Request Signing

- [Axios V4 signed request](https://medium.com/@joshua.a.kahn/calling-amazon-api-gateway-authenticated-methods-with-axios-and-aws4-6eeda1aa8696)
