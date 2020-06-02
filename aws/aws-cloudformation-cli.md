# AWS CLOUDFORMATION CLI

## Filter JSON Response
```
aws cloudformation describe-stacks |jq '.Stacks[0].StackId'
```

## Set Shell Variable From JSON
```
stackname=$(aws cloudformation describe-stacks | jq '.Stacks[0].StackName')
```

## Create Stack With Parameters
```
aws cloudformation create-stack \
  --stack-name myteststack \
  --template-body file://home/testuser/mytemplate.json \
  --parameters ParameterKey=Parm1,ParameterValue=test1 ParameterKey=Parm2,ParameterValue=test2
```

## Create Stack With Parameters And IAM_PROFILE
```
aws cloudformation create-stack \
  --stack-name logs \
  --template-body file://base-logging.yaml \
  --profile hss-sandbox \
  --region us-west-2 \
  --parameters ParameterKey=pNotifyEmail,ParameterValue="evan.harmon@harmonsoftwaresolutions.com" \
  --capabilities CAPABILITY_IAM
```

## Upload Stack Template To S3
here for convenience
`aws s3 cp test.txt s3://mybucket/test2.txt`

## Launch Stack Template With Params File
```
aws cloudformation create-stack \
  --stack-name test \
  --template-url https://s3.us-west-2.amazonaws.com/mybucket/mytemplate.yml \
  --cli-input-json file://myparams.json \
  --capabilities CAPABILITY_IAM
```

## Update Stack Template
```
$ aws cloudformation update-stack \
    --stack-name test \
    --template-url S3://mybucket/test2.yaml
```
