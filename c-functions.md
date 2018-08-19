# C FUNCTIONS

## Location
Functions are just pointers to code text

## Pointers Uses
Used for callbacks to other functions
Simulate classes and objects

## Pointer To A Function
- Write a normal function declaration: int callme(int a, int b)
- Wrap function name with pointer syntax: int (*callme)(int a, int b)
- Change the name to the pointer name: int (*compare_cb)(int a, int b)
