# AWS SAM LAMBDA DEBUGGING GOLANG

## Summary
Local debugging a golang lambda using the AWS SAM cli tool

## Build Delve for SAM cli use
```console
$ GOARCH=amd64 GOOS=linux go build -o $GOPATH/bin/linux/dlv github.com/derekparker/delve/cmd/dlv
```
