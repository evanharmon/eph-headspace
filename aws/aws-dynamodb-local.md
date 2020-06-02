# AWS DYNAMODB LOCAL

## Summary

Notes on using dynamodb local with Docker

## Resources

[Docs](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DynamoDBLocal.UsageNotes.html)
[Image](https://hub.docker.com/r/amazon/dynamodb-local)

## Start Locally

```console
docker run -p 8000:8000 amazon/dynamodb-local
```

## Local Web GUI

[github repo](https://github.com/deptno/dynamon)

use:

```console
npm install dynamodb-admin -g
docker run -p 8000:8000 amazon/dynamodb-local
export DYNAMO_ENDPOINT=http://localhost:8000
AWS_REGION=us-east-1 AWS_ACCESS_KEY_ID=LOCAL AWS_SECRET_ACCESS_KEY=LOCAL dynamodb-admin
```
