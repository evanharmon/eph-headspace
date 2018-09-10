# GOLANG VARIABLES
All golang variables are initialized to their respective zero values

## Declare A Package Wide Variable
unnested, then available to entire package
```golang
var port = ":1234"
```

## Declare Multiple Variables
```golang
var (
  port = ":1234"
  domain = "localhost"
)
```
## Unexported Variables
lowercase letter variables cannot be directly accessed outside package
```golang
var port = ":1234"
```

## Best Practice Variable Declaration
use `var` when not setting an initial value
```golang
var mystr string
mystr = ":1234"
```

## Unexported Identifiers Access
Can still be available outside the package to a calling function via closures / scope
Example (untested)
```golang
var port = ":1234"

func myFunc(newPort string) {
  port = newPort
}
```

## Pass Scoped Variables As Values To Goroutine
```golang
go func(mytype MyType, feed *Feed) {

}(mytype, feed)
```
