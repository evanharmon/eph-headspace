# MAKE

## Allow user to add / augment end of line
`$(OPTFLAGS)`

## Set Default Optional Value
`PREFIX?=/usr/local`

## Dynamically Create Sources
`SOURCES=$(wildcard src/**/*.c src/*.c)`

## Tell Make that a file depends on another file
```
all: ex19

ex19: object.o
```

## Code Flow
- Pre-Processor outputs processed c code
- Assembler creates code in machine language in OBJECT files
- Object files linked to get an executable
