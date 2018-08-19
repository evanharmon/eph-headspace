# ASSEMBLY COMPILE

## Compile ASM file to object file LINUX
`$ nasm -f elf -dELF_TYPE first.asm`

## Compile ASM file to object file OS X
needs brew install nasm for v2
needs export PATH=:"/usr/local/bin:${PATH}"
`$ nasm -f macho64 first.asm`

## GCC compile 32bit
`$ gcc -m32 -o first driver.c first.o asm_io.o`
