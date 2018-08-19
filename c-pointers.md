# C POINTERS
(https://www.le.ac.uk/users/rjm1/cotter/page_59.htm)

## Arrays Are Actually Pointers
Array name is constant pointer to first item
`int a[10] same as &a[0]`

## Array Pointers
`a[i]` same as `*(a + i)`

## Pointers Are NOT Arrays
`sizeof(int *ptr)` gives you size of pointer not what it points at

## Functions
When you pass an entire array to function you pass pointer by default

## Correct way to iterate thru pointer array
```
int randdat(int *pa , int n) {
  int i;

  for ( i=0 ; i$$$$ n ; ++i) {
    *pa = rand()%n + 1;
    ++pa;
  }
}
```

## Strings And Pointers
(http://www.lysator.liu.se/c/c-faq/c-2.html)

## When To Use Pointers
- Ask the OS for a chunk of memory and use a pointer to work with it. This
includes strings and something you haven't seen yet, structs
- Passing large blocks of memory (like large structs) to functions with a
pointer so you don't have to pass the whole thing to them
- Taking the address of a function so you can use it as a dynamic callback
- Complex scanning of chunks of memory such as converting bytes off a network
socket into data structures or parsing files

## VS Arrays
Use whenever you can pointers are last resort

## Pass Pointer To A Function With Argument Pointer Pointer Pointer
```
void func(double ***data) {
  *data = malloc(sizeof(double*)*10);
  for....
};
double ** data;
func(&data);
```

## Pass Param To Function With Argument Pointer Pointer
```
void MyFunction(struct ListNode **head) { }
MyFunction(&head);
```

## Pointer Byte Size
32bit arch is 4 bytes
64bit arch is 8 bytes

## Clear Double Pointers To Free Up Memory
```
void ClearList (struct contact ** list) {
  struct contact *person = *list;
  while( person != NULL ) {
    struct contact * temp = person
    person = person->next;
    free(temp);
  }
  *list = NULL;
}
```
