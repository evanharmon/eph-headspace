# GOLANG HTTP RESPONSE

## Summary

Notes on using golang's http response methods

## Dump Response For Debugging

```golang
requestDump, err := httputil.DumpRequest(req, true)
if err != nil {
  fmt.Println(err)
}
fmt.Println(string(requestDump))
```

## Runtime Error: Invalid Memory Address Or Nil Pointer Dereference

[SO](https://stackoverflow.com/questions/16280176/go-panic-runtime-error-invalid-memory-address-or-nil-pointer-dereference)
defer res.Body.Close() needs to come AFTER error checking

```golang
res, err := client.Do(req)

if err != nil {
    return nil, err
}
defer res.Body.Close()
```
