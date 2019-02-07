# GOLANG PATHS

## Summary

Notes on using paths with go

## Get Absolute Path From Relative Path

[SO](https://stackoverflow.com/questions/47261719/how-can-i-resolve-a-relative-path-to-absolute-path-in-golang)

```golang
base := "/home/bob"
fmt.Println(path.Join(base, "work/go", "src/github.com"))
```
