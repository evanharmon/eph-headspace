# C REFERENCING

## Referencing - Get the Address
Referencing means taking the address of an existing variable (using &) to set a
pointer variable. In order to be valid, a pointer has to be set to the address
of a variable of the same type as the pointer, without the asterisk:

```
int c1;
int* p1;
c1 = 5;
p1 = &c1;
//p1 references c1
```

## Dereferencing - Get the Value
Dereferencing a pointer means using the * operator (asterisk character) to
access the value stored at a pointer: NOTE: The value stored at the address of
the pointer must be a value OF THE SAME TYPE as the type of variable the pointer
"points" to, but there is no guarantee this is the case unless the pointer was
set correctly. The type of variable the pointer points to is the type less the
outermost asterisk

```
int n1;
n1 = (*p1);
```
