# C ++

## Summary

Notes on c++

## Casts

#### Generic Cast Form

```cpp
cast_name<cast_to_type>(item_to_cast)
```

#### Static Cast

no runtime checks performed. static_cast cannot cast away const or volatile.

```cpp
int * y = static_cast<int*>(malloc(10));
```

#### Malloc Casts

use a static cast

[C Casting](https://embeddedartistry.com/blog/2017/2/28/c-casting-or-oh-no-we-broke-malloc)
error: `cannot initialize a variable of type 'int *' with an rvalue of type 'void *'`

```cpp
int * p = static_cast<int*>(malloc(10));
```

#### Const Cast

````cpp
const_cast```
````
