# GDB

## Summary

Notes on using GDB

## Resources

[Tutorial](http://www.unknownroad.com/rtfm/gdbtut/gdbsegfault.html)

## Get Stacktrace After Segmentation Fault

```console
backtrace
```

## Set Breakpoint

```console
gdb a.out
break main.cpp:4
```

### Step In

```console
ni
```

### Examine Struct

```console
ptype myStruct
```

### Print Struct Member

```console
print myStruct.sampleRate
```
