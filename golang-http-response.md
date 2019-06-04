# GOLANG HTTP RESPONSE

## Summary

Notes on using golang's http response methods

## Dump Response For Debugging

```golang
postdump, err := httputil.DumpRequestOut(r, true)
if err != nil {
    return false, err
}
```
