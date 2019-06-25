# GOLANG TYPES

## Summary

Notes on working with golang's type system

## Resources

[Conversions](https://yourbasic.org/golang/convert-int-to-string/#string-to-int64)

## PRIMITIVES

Strings
Ints
Floats
Booleans

## Non-Primitives

Structs

## Structs

almost always should be mutating bc these are non-primitive

## Passing Primitives

always copy value to functions / methods

## Passing Reference Types

pass a copy of any reference type - the pointer to the data is already
part of the struct

## Convert string to int64

```golang
s := "97"
n, err := strconv.ParseInt(s, 10, 64)
if err == nil {
    fmt.Printf("%d of type %T", n, n)
}
```
