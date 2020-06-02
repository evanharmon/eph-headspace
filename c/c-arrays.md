# C ARRAYS

## Declare And Set Array
missing values will be set to 0
`int arr[10] = { 0, 1, 2, 3, 4, 5 };`

## Get Count Of Items In Statically Allocated Array
won't work for dynamic or checking argument of array inside a function
```
int arr[7] = { 50, 30, 20, 40, 70, 60, 80 };
int ln = sizeof(arr) / sizeof(arr[0]);
```

## Pass / Get Size Of Array In Function Parameter
When you pass an array to a function, it decays into a pointer to the first
element, at which point knowledge of its size is lost. Have to pass it in
function or use a struct with a capacity value
```
int x[20];
int ln = sizeof(x) / sizeof(*x);
```
