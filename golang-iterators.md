# GOLANG ITERATORS

## For Range
```golang
for _, e := range os.Environ() {
    pair := strings.Split(e, "=")
    fmt.Println(pair[0])
}
```
