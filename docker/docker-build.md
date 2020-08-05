# DOCKER BUILD

## Summary

Notes on building docker images

## Resources

- [ARG in Dockerfile FROM](https://www.jeffgeerling.com/blog/2017/use-arg-dockerfile-dynamic-image-specification)

## Build Image

```console
docker build -t "neovim-docker" .
```

## Build Docker Image From STDIN, Local Build Context

- [Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#pipe-dockerfile-through-stdin)

```bash
docker build -t -f- . <<EOF
FROM busybox
COPY somefile.txt .
RUN cat /somefile.txt
EOF
```

## Debug Using Multi-Stage Builds

- [Stop At Stage](https://docs.docker.com/develop/develop-images/multistage-build/#stop-at-a-specific-build-stage)

```console
docker build --target builder -t alexellis2/href-counter:latest .
```

## Build Docker Image With NO Context

```console
docker build - < Dockerfile
```

## AWS SDK Troubleshooting

If the docker build is complaining about aws env variables for the SDKs, use
the following flags to make sure a stale layer isn't in place

```console
docker build -t myimage \
  --no-cache \
  --force-rm \
  --build-arg AWS_ACCESS_KEY_ID \
  --build-arg AWS_SECRET_ACCESS_KEY \
  --build-arg AWS_SESSION_TOKEN \
  -f Dockerfile .
```
