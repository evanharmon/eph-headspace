# AWS PARAMETER STORE

## Summary

Notes on using Parameter Store provided by AWS Systems Manager

## Resources

## Tip

Don't enter in strings in quotes. Not necessary and makes parsing more difficult

## Example Responses

### Get Parameters

```json
{
  "Parameters": [
    {
      "Name": "MyStringListParameter",
      "Type": "StringList",
      "Value": "alpha,beta,gamma",
      "Version": 1,
      "LastModifiedDate": 1582154764.222,
      "ARN": "arn:aws:ssm:us-east-2:111222333444:parameter/MyStringListParameter"
    },
    {
      "Name": "MyStringParameter",
      "Type": "String",
      "Value": "Vici",
      "Version": 3,
      "LastModifiedDate": 1582156117.545,
      "ARN": "arn:aws:ssm:us-east-2:111222333444:parameter/MyStringParameter"
    }
  ],
  "InvalidParameters": ["MyInvalidParameterName"]
}
```
