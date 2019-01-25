# GOLANG DELVE

### Install Delve
```console
go get -u github.com/derekparker/delve/cmd/dlv
cd $GOPATH/src/github.com/go-delve/delve
make install
```

### Using Vim-Delve
Set breakpoint and run delve
```console
:DlvToggleBreakpoint
:DlvDebug
```

## Running Delve
[CLI](https://github.com/derekparker/delve/tree/master/Documentation/cli)

### Run Debugger From Main.Go File Location
```Console
dlv debug main.go
```

### Passing CLI Flags For Application
from package main file if in Neovim
```golang
:DlvDebug -- ./eph-music upload --file upload-file.txt
```

## Debugging
Print Function Arguments
```console
args
```

Print Struct Properties
```console
print req.Chunk.Content
```

Run Until Next Breakpoint / Program End
```console
$ continue
```

## Breakpoints
Set breakpoint on Main function
```console
break main.main
```

Set An Exact Breakpoint Line Number
```console
b endpoints.go:22
```

Set breakpoint in code [SO](https://stackoverflow.com/questions/35856911/how-can-i-set-breakpoints-by-the-sourcefile-line-number-in-delve)
```go
runtime.Breakpoint()
```
