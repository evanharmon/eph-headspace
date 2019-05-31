# GOLANG CGO

## Summary

Notes on using C with go

## Imports

common error is `could not determine kind of name for`
import of C CANNOT have a blank line above it, the below will fail

```golang
/*
#include <stdio.h>
int datspecialnumber() {
    return 2015;
}
*/

import "C"
import "fmt"
```

import of C cannot be inside a block of other imports, the below will fail

```golang
import (
	"C"
	"fmt"
)
```

correct import of C

```golang
// #cgo linux LDFLAGS: -L/usr/lib/gcc/x86_64-redhat-linux/7 -lstdc++ -ldl -lm
// #include <stdlib.h>
import "C"
```
