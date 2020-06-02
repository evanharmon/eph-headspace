# GOLANG DELVE DOCKER DEBUGGING

## Summary
Use the golang Delve debugger inside a docker container

## Resources
[Tutorial](https://mikemadisonweb.github.io/2018/06/14/go-remote-debug/)

## Example DockerFile Setup
```yaml
FROM golang:1.10-alpine
COPY root /
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH
RUN apk add --no-cache ca-certificates \
        dpkg \
        gcc \
        git \
        musl-dev \
    && mkdir -p "$GOPATH/src" "$GOPATH/bin" \
    && chmod -R 777 "$GOPATH" \
    && chmod +x /entrypoint.sh \
    && go get github.com/derekparker/delve/cmd/dlv
WORKDIR $GOPATH
ENTRYPOINT ["/entrypoint.sh"]
CMD ["dlv", "debug", "--headless", "--listen=:2345", "--api-version=2"]
```
entrypoint.sh contents
```bash
GO_WORK_DIR=${GO_WORK_DIR:-$GOPATH/src}
cd ${GO_WORK_DIR}
exec "$@"
```
## Example Docker-Compose
```yaml
version: '3'
services:
  app:
    container_name: "app"
    build: "./docker/go-debug"
    volumes:
      - ".:${GO_PROJECT_DIR}"
    environment:
      GO_WORK_DIR: "${GO_PROJECT_DIR}/app"
    ports:
      - "8080:8080"
      - "2345:2345"
    security_opt:
      - "seccomp:unconfined"
```

## Could Not Launch Process Error Fork/Exec
pass to docker run `--security-opt=seccomp:unconfined`
