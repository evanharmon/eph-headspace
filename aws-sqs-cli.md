# AWS SQS CLI

## Summary

Notes on using the SQS cli tool

## Resources

- [CLI Docs](https://docs.aws.amazon.com/cli/latest/reference/sqs/)

### Queues

#### Create LIFO Queue

```console
aws sqs create-queue --queue-name my-new-queue
```

### Messages

#### Receive Messages

##### Download SQS Messages To JSON

```console
export SQS_QUEUE_URL='https://sqs.us-east-1.amazonaws.com/111111111111/MyQueue'
aws sqs receive-message \
  --queue-url $SQS_QUEUE_URL \
  --attribute-names All \
  --message-attribute-names All \
  --max-number-of-messages 10 > receive-messages.json
```

##### Download Single SQS Message To JSON By Message ID

not possible

##### Grab Example Attributes For Queue

```console
aws sqs receive-message \
  --queue-url https://sqs.us-east-1.amazonaws.com/111111111111/my-queue \
  --message-attribute-names All
```

#### Send Messages

##### Create Template Message File / CLI Skeleton

```console
aws sqs send-message --generate-cli-skeleton > message-skeleton.json
```

```json
{
  "QueueUrl": "",
  "MessageBody": "",
  "DelaySeconds": 0,
  "MessageAttributes": {
    "KeyName": {
      "StringValue": "",
      "BinaryValue": null,
      "StringListValues": [""],
      "BinaryListValues": [null],
      "DataType": ""
    }
  },
  "MessageDeduplicationId": "",
  "MessageGroupId": ""
}
```

##### Send SQS Message To Queue

```console
aws sqs send-message --cli-input-json file://cli-input.json
```

#### Format Messages For Send Message Batch

may need to capitalize messages.json file keys

```console
export Q_URL="https://sqs.us-east-1.amazonaws.com/111111111111/my-queue"
jq '.Messages | map(. + { Id: .MessageId, MessageBody: .Body } | del(.Body,.MD5OfMessageAttributes,.MD5OfBody,.ReceiptHandle,.Attributes,.MessageId)) | { QueueUrl: env.Q_URL, Entries: . }' messages.json > cli-input.json
```
