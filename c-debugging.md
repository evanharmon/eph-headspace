# C DEBUGGING

## Mac
`lldb ./ex1`

## Linux
`$ gdb ./ex1`

## Set Breakpoint lldb
`$ lldb breakpoint set --file file.c --line 12`

## Set Breakpoint by function name lldb
`$ lldb breakpoint set --name myfunction`

## Set Breakpoint in code
```
#include <signal.h>
raise(SIGINT);
```
