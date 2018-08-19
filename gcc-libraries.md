# GCC LIBRARIES

## Check Executable Linked Libraries

`$ ldd myprog`

## Link Library File
-l must link directory if outside project with -L as well
`$ gcc sqroot.c -o sqroot -lm`

## Link Library Directory
-L
`$ gcc sqroot.c -o sqroot -L/home/user/libs -lm`
