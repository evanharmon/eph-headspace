# C PASSING

## Pass By Value
`$ void fcn(int n) {}`
When passing by value, you get a copy of the value. If you change the value in
your function, the caller still sees the original value regardless of your
changes

## Pass By Pointer To Value
`$ void fcn(int* n) {}`
Passing by pointer gives you a copy of the pointer - it points to the same
memory location as the original. This memory location is where the original is
stored. This lets you change the pointed-to value. However, you can't change the
actual pointer to the data since you only received a copy of the pointer

## Pass Pointer To Pointer To Value
`$ void fcn(int** n) {}`
You get around the above by passing a pointer to a pointer to a value. As above,
you can change the value so that the caller will see the change because it's the
same memory location as the caller code is using. For the same reason, you can
change the pointer to the value. This lets you do such things as allocate memory
within the function and return it; `&arg2 = calloc(len);`. You still can't change
the pointer to the pointer, since that's the thing you recieve a copy of
