# C STACK

## Definition
Special region of memory to hold temporary variables, each function created as
locals to that function

## Examples In Functions
```
char action
int id
```

## Memory
Cleared off the stack once function exits

## Is It On The Stack?
If you get a block of memory from malloc, and have the pointer on the stack,
the when function exits the pointer will be popped off stack and most

## Overflow
If you put too much data on the stack (like large structs and arrays), you can
cause a stack overflow, and program will abort. Use the heap instead

## Segmentation Fault
If you take a pointer from something on the stack, then pass or return it from
your function, then the function will segmentation fault because the actual
data will pop off and disappear. Pointer is now pointing at dead space
