# GOLANG ATHENS

Package manager and proxy. At the time of this writing, the proxy must be
started manually

## SETUP

### Install

```console
go get -u github.com/gomods/athens/cmd/proxy
cd ~/go/src/github.com/gomods/athens/cmd/proxy
go install
proxy &
```

### Environmental Variables

```bash
export GO111MODULE=auto
export GOPROXY=http://127.0.0.1:3000
```

### Script To Install

```bash
if [ -d $GOPATH/src/github.com/gomods/athens ]; then
  go get -u github.com/gomods/athens/cmd/proxy
fi
```

## Manually Run Proxy

### Start Proxy

```console
proxy
```

### Script To Start Proxy

```bash
if lsof -i :3000; then
  echo "Gomods Proxy already running"
else
  proxy &
fi
```

## USE

Manually set `export GO111MODULE=on` in your shell

## Download Dependencies

```console
go run .
```

## Clear Cache

```console
sudo rm -fr $(go env GOPATH)/pkg/mod
```

## Run Athens From Local Disk Storage With Docker

[Instructions](https://docs.gomods.io/install/shared-team-instance/)

```
export ATHENS_STORAGE=~/athens-storage
mkdir -p $ATHENS_STORAGE
docker run -d -v $ATHENS_STORAGE:/var/lib/athens \
   -e ATHENS_DISK_STORAGE_ROOT=/var/lib/athens \
   -e ATHENS_STORAGE_TYPE=disk \
   --name athens-proxy \
   --restart always \
   -p 3000:3000 \
   gomods/athens:latest
```
