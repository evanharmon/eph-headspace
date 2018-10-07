# GOLANG DELVE

## Install Delve
```console
$ brew install go-delve/delve/delve
```

## Run Debugger From Main.Go File Location
```Console
$ dlv debug main.go
```

## Set An Exact Breakpoint Line Number
```console
$ b endpoints.go:22
```

## CLI Commands
[CLI](https://github.com/derekparker/delve/tree/master/Documentation/cli)

Print Function Arguments
```console
$ args
```

Print Struct Properties
```console
$ print req.Chunk.Content
```

Run Until Next Breakpoint / Program End
```console
$ continue
```

## Vim-Delve
Set breakpoint and run delve
```console
:DlvToggleBreakpoint
:DlvDebug
```

## Passing CLI Flags For Application
```golang
:DlvDebug -- ./eph-music upload --file upload-file.txt
```
