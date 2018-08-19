# C MEMORY
The easiest way to keep this straight is with this mantra:
If you didn't get it from malloc or a function that got it from malloc, then
it's on the stack

- If you get a block of memory from malloc, and have that pointer on the stack,
then when the function exits, the pointer will get popped off and lost
- If you put too much data on the stack (like large structs and arrays) then you
can cause a "stack overflow" and the program will abort. In this case, use the
heap with malloc
- If you take a pointer to something on the stack, and then pass that or return
it from your function, then the function receiving it will "segmentation fault"
(segfault) because the actual data will get popped off and disappear. You'll be
pointing at dead space
