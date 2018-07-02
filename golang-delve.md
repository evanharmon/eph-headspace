# Install delve
go get -u github.com/derekparker/delve/cmd/dlv
cd $GOPATH/src/github.com/derekparker/delve
export GOBIN=$GOPATH/bin
Make install

## Run Debugger from main.go file location
dlv debug

## Set an exact breakpoint line number
dlv debug
$ b endpoints.go:22
