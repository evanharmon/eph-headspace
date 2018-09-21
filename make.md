# MAKE

## Allow User To Add / Augment End Of Line
`$(OPTFLAGS)`

## Set Default Optional Value
`PREFIX?=/usr/local`

## Dynamically Create Sources
`SOURCES=$(wildcard src/**/*.c src/*.c)`

## Tell Make That A File Depends On Another File
```
all: ex19

ex19: object.o
```

## Code Flow
- Pre-Processor outputs processed c code
- Assembler creates code in machine language in OBJECT files
- Object files linked to get an executable

## .PHONY
not associated with a file
