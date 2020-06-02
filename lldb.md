# C DEBUGGING

## Mac

```console
lldb ./ex1
```

## Set Breakpoint lldb

```console
breakpoint set --file file.c --line 12
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
