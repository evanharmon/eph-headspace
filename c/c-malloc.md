# C MALLOC

## Do Not Cast To Pointer
`https://stackoverflow.com/questions/14768230/malloc-for-struct-and-pointer-in-c`
Bad
`struct Vector *y = (struct Vector*)malloc(sizeof(struct Vector));`
Good
`struct Vector *retVal = malloc (sizeof (struct Vector));`
