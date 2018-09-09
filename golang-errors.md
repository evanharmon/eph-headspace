# GOLANG ERRORS
[DOCS](https://golang.org/pkg/errors/)

## Return Error With Formatting
```golang
err := beforeTestGetEnv()
if err != nil {
  fmt.Errorf("Before failed: %v", err)
}
```

## Check For Error Without Redeclaring
Note other variables returned from function will have to not be in scope to
the rest of the function
```golang
if err := beforeTestGetEnv(); err != nil {
  t.Errorf("Before failed: %v", err)
}
```
