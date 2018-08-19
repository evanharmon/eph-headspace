# C COMPILERS
Compiles but do not link or create executable

## Compiling Creates An Object .o File
`gcc -c driver.c`

## Compile To Executable
`gcc -o hello hello.c`

## cc
`cc main.c -o app`

## Create o Files For Clang
DNDEBUG is for zed's debug macros
```
cc -Wall -g -DNDEBUG -c -o ex22.o ex22.c
cc -Wall -g -DNDEBUG ex22_main.c ex22.o -o ex22_main
```
