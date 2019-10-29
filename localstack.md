# LOCAL STACK

## Summary

Notes on using local stack docker containers with k8s

## Resources

[Docs](https://localstack.cloud/)
[Github](https://github.com/localstack/localstack)
[Customize Endpoing for Localstack](https://docs.aws.amazon.com/sdk-for-go/api/aws/endpoints/)

## INSTALL

Installation involves git cloning and running docker-compose up to pull images

```console
git clone https://github.com/localstack/localstack.git $HOME/code
cd $HOME/code/localstack
TMPDIR=/private$TMPDIR docker-compose up
```

## AWS SERVICES

#### SQS Create Queue

create queue

```console
aws --endpoint-url=http://localhost:31000 sqs create-queue --queue-name my-best-queue
```

#### SQS Send Messages

note the queue fully qualified domain name with `/queue/` in path.
`aws --endpoint-url=http://localhost:31000 --profile="default" sqs list-queues` to get queue url's

```console
export AWS_PROFILE="default"
export Q_NAME="myqueue" 
export ENDPOINT_URL="http://localhost:31000"
aws --endpoint-url=$ENDPOINT_URL \
	sqs send-message-batch \
	--queue-url $ENDPOINT_URL/queue/$Q_NAME \
	--entries file://cli-input.json
```
