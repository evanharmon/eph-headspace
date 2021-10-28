# AWS LAMBDA CLI

## Test Lambda Function Manually

```console
$ aws lambda invoke \
    --invocation-type RequestResponse \
    --function-name myLambdaTestEndpoint \
    --region us-east-1 \
    --payload file://$PWD/input.json \
    --profile hss-prod output.txt
```

## Update Lambda Function

```console
$ aws lambda update-function-code \
    --zip-file=fileb://file_name.zip \
    --function-name cloudguru-lab-1
```

## Publish Lambda Function

```
$ aws lambda update-function-code \
    --zip-file=fileb://file_name.zip \
    --function-name cloudguru-lab-1
    --publish
```

## Update Lambda Function Config

```console
$ aws lambda update-function-configuration \
    --function-name cloudguru-lab-1
    --handler csv_read.handler
```

### Find Lambdas Using Layer

```console
aws lambda list-functions \|
  jq -r '.Functions[] | {name: .FunctionName, layerArns: .Layers[]? | select(.Arn | contains("mypkg"))}’
```

### List Security Groups Used By Lambdas

```console
aws lambda list-functions | jq -c '.Functions[] | {FunctionArn, SecurityGroups: (.VpcConfig.SecurityGroupIds[]? // null) }'
```
