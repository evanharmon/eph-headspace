# C NETWORK HELPERS

## Read
`int read(int fildes, const void *buf, int nbyte);`

## Write
`int write(int fildes, const void *buf, int nbyte);`

## Fork
returns process id
`int fork(void);`

## Null Bytes BZERO
takes string and sets nbytes to NULL
`void bzero(void *s, int nbyte);`

## BCMP Compare Bytes
`int bcmp(const void *s1, const void *s2, int nbyte);`

## BCOPY Copy Bytes
`void bcopy(const void *s1, void *s2, int nbyte);`

## Memset Set Struct Variables
Source, Character to set nbytes, nbyte # of nbytes
`void *memset(void *s, int c, int nbyte);`
