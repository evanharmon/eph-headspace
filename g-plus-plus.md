# g++

## Summary

Notes on using the `g++` compiler

## Resources

[C++ and C Files](https://www.toptal.com/c-plus-plus/c-plus-plus-understanding-compilation)

## Basic Single File Program

creates an executable called `main.out`

```console
g++ main.cpp
```

## Custom Executable Name

```console
g++ binaryheaps.cc -o test
```

## Compile In to Object Code Files

```console
g++ -c main.cpp
```

## Link Object Files Creating Executable

```console
g++ -o main main.o second.o
```

## Compile And Link Creating Executable

```console
g++ -c main.cpp -o main
```

## Compile And Link With Debug Symbols

```console
g++ -g main.cpp -o main
```
