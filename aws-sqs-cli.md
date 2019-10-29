# AWS SQS CLI

## Summary

Notes on using the SQS cli tool

## Create LIFO Queue

```console
aws sqs create-queue --queue-name my-new-queue
```

## Download SQS Messages To JSON

```console
export SQS_QUEUE_URL='https://sqs.us-east-1.amazonaws.com/111111111111/MyQueue'
aws sqs receive-message \
  --queue-url $SQS_QUEUE_URL \
  --attribute-names All \
  --message-attribute-names All \
  --max-number-of-messages 10 > receive-messages.json
```

## Download Single SQS Message To JSON By Message ID
not possible

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

## Format Messages For Send Message Batch
```console
export Q_URL="https://sqs.us-east-1.amazonaws.com/111111111111/my-queue"
jq '.Messages | map(. + { Id: .MessageId, MessageBody: .Body } | del(.Body,.MD5OfMessageAttributes,.MD5OfBody,.ReceiptHandle,.Attributes,.MessageId)) | { QueueUrl: env.Q_URL, Entries: . }' messages.json > cli-input.json
```
