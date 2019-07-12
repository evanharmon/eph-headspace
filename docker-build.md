# DOCKER BUILD

## Summary

Notes on building docker images

## Build Image

```console
docker build -t "neovim-docker" .
```

## Build Docker Image From STDIN, Local Build Context

[Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#pipe-dockerfile-through-stdin)

```bash
docker build -t -f- . <<EOF
FROM busybox
COPY somefile.txt .
RUN cat /somefile.txt
EOF
```
