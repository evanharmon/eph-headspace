# AWS API GATEWAY FAQs

## Summary

## Resources

## Common FAQs

### Lambda Proxy

#### Service / Operation Name Not Authorized

error message

```
apigateway Unable to determine service/operation name to be authorized
```

If using Lambda proxy, it has to be a `post`!

#### Invalid permissions on Lambda function

```
Execution failed due to configuration error: Invalid permissions on Lambda function
```
