# DOCKERFILE

## Summary

Notes on working with Dockefiles

## Resources

[Docs](https://docs.docker.com/engine/reference/builder/)
[Multistage Builds](https://docs.docker.com/develop/develop-images/multistage-build/)
[Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)

## Quiet Front-End no prompts

```
RUN DEBIAN_FRONTEND=noninteractive apt-get update
```

## Send Arguments to Dockerfile on Build

```console
docker build --build-arg userHome=$HOME .
```

## ARG In Dockerfiles

[Docs](https://docs.docker.com/engine/reference/builder/#arg)
ENV overrides ARG

#### Use Argument in DockerFile

```
ARG userHome
ADD $userHome/.config /home/dev
```

## Change Directory

`WORKDIR /home/dev/.bin`

## Change User In Dockerfile

`USER dev2`

## ENV In Dockerfiles

[Docs](https://docs.docker.com/engine/reference/builder/#arg)
ENV overrides ARG

#### Set Environment Variable In Dockerfile

`ENV HOSTNAME nvim`

## Run a script In A Dockerfile

`CMD ["/bin/zsh"]`

## Leveraging Build Cache / COPY

[Docker](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#leverage-build-cache)

```
For the ADD and COPY instructions, the contents of the file(s) in the image are
examined and a checksum is calculated for each file. The last-modified and
last-accessed times of the file(s) are not considered in these checksums. During
the cache lookup, the checksum is compared against the checksum in the existing
images. If anything has changed in the file(s), such as the contents and
metadata, then the cache is invalidated.
```

## Copy a file/directory

Trailing slash is considered a directory
`COPY hss-cfg/ .hss-cfg/`

## Keep Container Running
extend to a docker run with entrypoint flag
```
FROM ubuntu:latest

ENTRYPOINT ["tail", "-f", "/dev/null"]
```

## Extend \$PATH

```
ENV PATH="/root/go/bin:${PATH}"
```

## Expose Port

```
EXPOSE 8080/tcp
```

## Multistage Builds

Use multiple images in a Dockerfile and copy files between them

```
FROM eph-bin/base:latest AS bins
FROM eph-nvim/base:latest
COPY --from=bins /root/bins /root/bins
```

## Set ENV Variable From ARG

```docker
ARG A_VARIABLE
ENV an_env_var=$A_VARIABLE
```

## Build Dockerfile From Std In With No Build Context

[Guide](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#pipe-dockerfile-through-stdin)
can speed up builds by not using files in the directory

```console
cat Dockerfile | docker build my-image/base:latest -
```

## Fail On Any Stage In Pipe Command

```
If you want the command to fail due to an error at any stage in the pipe, prepend set -o pipefail && to ensure that an unexpected error prevents the build from inadvertently succeeding. For example:

RUN set -o pipefail && wget -O - https://some.site | wc -l > /number
```

## Unset ENV Variables Not To Persist In Container

Every `ENV` docker command creates a layer and will exist in the resulting
docker container. To create a non-persisting env variable, use a chained `RUN`
command.

```dockerfile
RUN export ADMIN_USER="mark" \
    && echo $ADMIN_USER > ./mark \
    && unset ADMIN_USER
```

## Inspect `.dockerignore` And Build Context

[SO](https://stackoverflow.com/questions/43808558/docker-command-option-to-display-or-list-the-build-context)
Note: won't show dotfiles

install `ncdu`. `brew install ncdu` or `yum install -y ncdu`

```console
ncdu -X .dockerignore
```

## Add vs Copy

- [Add Docs](https://docs.docker.com/engine/reference/builder/#add)
- [Copy Docs](https://docs.docker.com/engine/reference/builder/#copy)

```
Note: If you build using STDIN (docker build - < somefile), there is no build context, so COPY can’t be used
```
