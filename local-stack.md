# LOCAL STACK

## Summary

Notes on using local stack docker containers with k8s

## Resources

[Docs](https://localstack.cloud/)
[Github](https://github.com/localstack/localstack)

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
aws --endpoint-url=http://localhost:4576 sqs create-queue --queue-name my-best-queue
```

#### SQS Send Messages

note the queue fully qualified domain name with `/queue/` in path.
`aws --endpoint-url=http://localhost:31000 --profile="default" sqs list-queues` to get queue url's

```console
aws --endpoint-url=http://localhost:31000 --profile="default" \
	sqs send-message-batch \
	--queue-url http://localhost:31000/queue/my-queue-name \
	--entries file://cli-input-10.json
```
