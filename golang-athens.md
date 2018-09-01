# GOLANG ATHENS
Package manager and proxy. At the time of this writing, the proxy must be
started manually

## Install
`go get -u github.com/gomods/athens/cmd/proxy`

## Environmental Variables
```
export GO111MODULE=auto
export GOPROXY=http://127.0.0.1:3000
```

## Start Proxy
`proxy`

## Download Dependencies
`go run .`

## Script To Install
```
if [ -d $GOPATH/src/github.com/gomods/athens ]; then
  go get -u github.com/gomods/athens/cmd/proxy
fi
```

## Script To Start Proxy
```
if lsof -i :3000; then
  echo "Gomods Proxy already running"
else
  proxy &
fi
```

## Clear Cache
`sudo rm -fr $(go env GOPATH)/pkg/mod`
