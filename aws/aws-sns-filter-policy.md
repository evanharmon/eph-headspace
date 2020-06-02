# AWS SNS FILTER POLICY

## Summary

Notes on working with sns subscription filter policies.
Subscription filters DO NOT act on the message body. Only on the message
attributes

## Resources

[AWS Blog Tutorial](https://aws.amazon.com/getting-started/tutorials/filter-messages-published-to-topics/)
[AWS DOCS](https://docs.aws.amazon.com/sns/latest/dg/sns-message-filtering.html)
[AWS Message Attributes](https://docs.aws.amazon.com/sns/latest/dg/SNSMessageAttributes.html)

## Filter Syntax

## Filter By Mandatory Key

```javascript
{
  "color": ["blue", "green"]
}
```
