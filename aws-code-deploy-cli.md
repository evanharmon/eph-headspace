# AWS CODE DEPLOY CLI

## General
`$ aws deploy list-applications`
`$ aws deploy list-deployments`
`$ aws deploy list-deployment-groups --application-name dianabresson.com-www`

## Deploy S3 bucket for codedeploy
```
$ aws deploy push \
    --application-name myapp \
    --s3-location s3://mybucket/myapp \
    --source mypath
```

## S3 Deployment
```
$ aws deploy create-deployment \
    --application-name myapp \
    --deployment-group-name mydeploygroup \
    --ignore-application-stop-failures \
    --s3-location bundleType=tar,bucket=BUCKET,key=KEY \
    --description "Ignore ApplicationStop failures due to broken script"
```

## Github Deployment
```
$ aws deploy create-deployment \
    --application-name myapp \
    --deployment-group-name mygroup \
    --ignore-application-stop-failures \
    --github-location commitId=`git rev-parse HEAD`,repository=ACCOUNT/PROJECT \
    --description "Ignore ApplicationStop failures due to broken script"
```
