# GOLANG LOGGING

## Summary

Notes on using log methods and logging across packages

## Resources

[Package Level Loggers Done Right](https://dave.cheney.net/2017/01/23/the-package-level-logger-anti-pattern)

## Log the Pointer Value

```
// &s is mem location \**s,
//s is *something,
//*s is something the actual value
fmt.Printf("%v %p %v\n", &s, s, *s)
```
