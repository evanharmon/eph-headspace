# AWS LAMBDA CLI

## Test Lambda Function Manually
```
$ aws lambda invoke \
    --invocation-type RequestResponse \
    --function-name myLambdaTestEndpoint \
    --region us-east-1 \
    --payload file://$PWD/input.json \
    --profile hss-prod output.txt
```

## Update Lambda Function
```
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
```
$ aws lambda update-function-configuration \
    --function-name cloudguru-lab-1
    --handler csv_read.handler
```
