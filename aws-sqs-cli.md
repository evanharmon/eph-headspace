# AWS SQS CLI

## Summary

Notes on using the SQS cli tool

## Download SQS Message To JSON

```console
export SQS_QUEUE_URL='https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue'
aws sqs receive-message \
  --queue-url $SQS_QUEUE_URL \
  --attribute-names All \
  --message-attribute-names All \
  --max-number-of-messages 1
```
