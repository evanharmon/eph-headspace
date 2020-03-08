# GOLANG GOTCHAS

## Summary

Notes on various golang gotchas and common errors

### Multiple Value In Single-Value Context

```golang
a := json.Marshal(variable)
```

needs to be

```golang
a, _ := json.Marshal(variable)
```

### EOF error on request

Means the request body is empty

### Type Is Not An Expression

thing to the right of `=` must evaluate to a value.

valid declarations

```golang
type FileManager {}

func main() {
  var f FileManager
  var f = FileManager{}
  s := FileManager{}
}
```

### invalid Memory Address or Nil Pointer Dereference

if using a method with receiver - remove the asterisk

change `func (*mockUploader) myMethod() {}` to `func (mockUploader) myMethod() {}`
