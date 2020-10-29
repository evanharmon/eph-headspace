# CPP MEMORY MANAGEMENT

## Summary

Notes on memory management in c++

## Resources

- [Dynamic Memory Management](https://www.learncpp.com/cpp-tutorial/69-dynamic-memory-allocation-with-new-and-delete/)
- [Dynamically Allocated Arrays](https://www.learncpp.com/cpp-tutorial/6-9a-dynamically-allocating-arrays/)

## Types Of Memory Management

Static and Automatic Memory Allocation have two things in common:

- size of variable / array must be known at compile time
- memory allocation / deallocation happens automatically
- on the stack

### Static Memory Allocation

Static and global variables

- persist through life of program

### Automatic Memory Allocation

Function parameters and local variables

- allocated on block entry
- freed on block exit

### Dynamic Memory Allocation

Memory allocated by the Operating System on the heap

### Operator New

new can fail. Always check for nullptr afterwards. The OS could fail to
allocate memory

## Memory Leaks

When a program loses the address of dynamically allocated memory.
The memory can not be deleted / returned to the operating system

This can happen by assigning a new value to a pointer.

```cpp
int value = 5;
int *ptr = new int; // allocate memory
ptr = &value; // old address lost
```

delete it first!

```cpp
int value = 5;
int *ptr = new int; // allocate memory
delete pr;
ptr = &value;
```
