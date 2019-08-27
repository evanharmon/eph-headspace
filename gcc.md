# GCC

## 32 bit on 64 bit

Centos packages
`$ yum reinstall glibc.i686 glibc-devel.i686 libstdc++-devel.i686`

# Compile

`$ gcc -m32 -o first first.o asm_io.o driver.c`

## Build GCC8 On Debian

[Blobfolio](https://blobfolio.com/2018/12/using-docker-as-a-build-environment/)
