# C DEBUGGING

## Mac

```console
lldb ./ex1
```

## Run

Remember this has to be entered after setting a breakpoint!
Otherwise you'll see the error `error: invalid process`

```console
run
```

## Set Breakpoint lldb

```console
breakpoint set --file main.c --line 12
```

## Set Breakpoint by function name lldb

```console
breakpoint set --name myfunction
```

## Set Breakpoint in code

```c
#include <signal.h>
raise(SIGINT);
```

## Show Call Stack

```console
bt
```

## GUI MODE

#### Launch Curses GUI

```console
gui
```

## Quit GUI Mode

option + c

## Show Variables In Frame

```console
frame variable
```

## Examine Struct Field

```console
print wav.sampleRate
```

## Print Contents Of Memory Address

```console
memory read -s1 -fu -c10000 0xb0987654 --force
```

## Print Object

```console
po blabhlah
```

## Step In

```console
step
```

## Step Over

```console
next
```
