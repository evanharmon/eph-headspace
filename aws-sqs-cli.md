# AWS SQS CLI

## Summary

Notes on using the SQS cli tool

## Download SQS Messages To JSON

```console
export SQS_QUEUE_URL='https://sqs.us-east-1.amazonaws.com/111111111111/MyQueue'
aws sqs receive-message \
  --queue-url $SQS_QUEUE_URL \
  --attribute-names All \
  --message-attribute-names All \
  --max-number-of-messages 10 > receive-messages.json
```

## Create Template Message File

```console
aws sqs send-message --generate-cli-skeleton > message-skeleton.json
```

## Grab Example Attributes For Queue

```console
aws sqs receive-message \
  --queue-url https://sqs.us-east-1.amazonaws.com/111111111111/my-queue \
  --message-attribute-names All
```

## Send SQS Message To Queue

```console
aws sqs send-message --cli-input-json file://my-test-message.json
```
