# GOLANG ATHENS
Package manager and proxy. At the time of this writing, the proxy must be
started manually

## SETUP

### Install
`go get -u github.com/gomods/athens/cmd/proxy`

### Environmental Variables
```
export GO111MODULE=auto
export GOPROXY=http://127.0.0.1:3000
```

### Script To Install
```
if [ -d $GOPATH/src/github.com/gomods/athens ]; then
  go get -u github.com/gomods/athens/cmd/proxy
fi
```

## Manually Run Proxy

### Start Proxy
`proxy`

### Script To Start Proxy
```
if lsof -i :3000; then
  echo "Gomods Proxy already running"
else
  proxy &
fi
```

## USE
Manually set `export GO111MODULE=on` in your shell

## Download Dependencies
`go run .`

## Clear Cache
`sudo rm -fr $(go env GOPATH)/pkg/mod`
