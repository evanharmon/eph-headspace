## GCC OPTIONS

## Name Output File

-o
`$ gcc hello.c -o hello`

## Put In Different Folder

`$ gcc hello.c -o ~/bin/hello`

## Make Object File

-c ignores any library linking flags
`$ gcc -c db.c -o db.o`

## Link Object Files To Make Executable

```
gcc -c main.c -o main.o
gcc -c db.c -o db.o
gcc main.o db.o -o myprog
```
