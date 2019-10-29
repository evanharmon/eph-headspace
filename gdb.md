# GDB

## Summary

Notes on using GDB

## Resources

[Tutorial](http://www.unknownroad.com/rtfm/gdbtut/gdbsegfault.html)
[Install Tutorial](www.gdbtutorial.com/tutorial/how-install-gdb)

## Pass Commandline Arguments To Program

```console
gdb --args myexecutable arg1 arg2 arg3
```

## Get Stacktrace After Segmentation Fault

```console
backtrace
```

## Run

```console
run
```

## Breakpoints

#### List Breakpoints

```console
info breakpoints
```

#### Set Breakpoint

```console
gdb a.out
break main.cpp:4
```

#### Disable Breakpoint

```console
disable b 13
```

### Step In

```console
ni
```

## Step Over

```console
next
```

### Examine Struct

```console
ptype myStruct
```

## Print Variable

```console
print pSampleData
```

### Print Struct Member

```console
print myStruct.sampleRate
```

## Set Safe Path

```console
set auto-load safe-path /
```

## Move Past SIGTRAPS

[SO](https://stackoverflow.com/questions/9837594/sigtrap-despite-no-set-breakpoints-hidden-hardware-breakpoint)

in gdb, set each sigtrap as a hardware breakpoint at the memory location

```console
f 0
hbreak *0x4003ed70
```

delete each breakpoint

```console
info breakpoint
disable breakpoint 11
continue
```
