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

## Allow Function Caller To Handle Err
```golang
return nil, err
```

## Use Field From Custom Error Struct
[Example](https://godoc.org/google.golang.org/api/googleapi#Error)
```golang
err := bkt.Create(ctx, projectID, nil)
gerr, ok := err.(*googleapi.Error)
if err != nil && ok && gerr.Code != 409 {
  return err
}

return nil
```

## Add String Context To Error
```golang
errors.wrap(err, "read failed")
```
