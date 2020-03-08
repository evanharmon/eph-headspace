# GOLANG STRUCTS

## Summary

Notes on working with golang structs

## Resources

[OmitEmpty Tags](https://www.sohamkamani.com/blog/golang/2018-07-19-golang-omitempty/)

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

## Initialize Struct

initializing a custom type

```golang
type employee struct {
  FirstName string
  LastName string
}

function myFunc(first, last string) {
  emp := employee{FirstName: first, LastName: last}
}
```
