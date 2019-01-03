# SERVERLESS GOLANG DEBUGGING

## Summary
Local debugging a golang lambda using serverless and the AWS SAM cli tool

## Installs
golang
node
```console
$ pip3 install aws-sam-cli
$ npm install -g serverless
$ serverless plugin install --name serverless-sam
```

## Create SAM template.yml
```console
$ serverless sam export --output template.yml
```

## Build Delve for SAM cli use
```console
$ GOARCH=amd64 GOOS=linux go build -o $GOPATH/bin/linux/dlv github.com/derekparker/delve/cmd/dlv
```

## Start Local SAM Api Gateway
GIVING python error on 'strict'
```console
$ sam local start-api -d 5986 --debugger-path $GOPATH/bin
```
