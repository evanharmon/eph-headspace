# C TYPES
beware type aliasing and pointers
(http://www.viva64.com/en/a/0050/)

The next possible problem is type aliasing. This occurs when two variables
point to the same bit of memory. This is a problem because the C compiler will
assume that two objects with different effective types will not reference
overlapping memory locations

## zero null byte
`Char = '\0'`

## String is an array of chars in C
`char[] = "string"`

## no bool type
Computer only thinks in integers
0 false, 1 true
