# AWS LAMBDA DOCKER GOLANG DEBUGGING

## Summary
Local debugging a golang lambda using lambci lambda docker and delve

## Installs
golang
Delve

## Docker Setup
[Repo Doc](https://github.com/lambci/docker-lambda)

## Build Linux Delve For Docker
From your project repo folder:
```console
$ GOARCH=amd64 GOOS=linux go build -o $PWD/bin/dlv github.com/derekparker/delve/cmd/dlv
```

## Run Docker Container With Lambda With Bash
requires unconfined security
```console
docker run \
  -v ${PWD}:/go/src/github.com/evanharmon/my-go-project \
  -p 40000:40000 \
  --security-opt seccomp=unconfined \
  -it --rm \
  lambci/lambda:build-go1.x bash
```

## Run Delve with Lambda Event In Docker Container
requires unconfined security
```console
docker run \
  -v ${PWD}:/go/src/github.com/evanharmon/my-go-project \
  -p 40000:40000 \
  --security-opt seccomp=unconfined \
  -it --rm \
  lambci/lambda:build-go1.x \
  /go/src/github.com/evanharmon/my-go-project/bin/dlv debug \
    --headless --listen=:40000 --api-version=2 \
    /go/src/github.com/evanharmon/my-go-project/main.go
```
