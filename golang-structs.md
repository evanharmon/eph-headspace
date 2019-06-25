# GOLANG STRUCTS

## Summary

Notes on working with golang structs

## Inline Define / Anonymous Struct

[Golangbot](https://golangbot.com/structs/)

```golang
emp3 := struct {
    firstName, lastName string
    age, salary         int
}{
    firstName: "jon",
    lastName:  "smith",
    age:       31,
    salary:    5000,
}
```
