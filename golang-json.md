# GOLANG JSON

## Summary

Notes on working with JSON in golang

## Convert JSON to GO Struct

[JSON-to-Go](https://mholt.github.io/json-to-go/)

## Parse JSON To Interface

```golang
var res interface{}
err := json.Unmarshal([]byte("mybites"), &res)
```

## Parse Golang Back To JSON

```golang
spec, err := json.Marshal(chain)
```

## Omit Field If Empty

```golang
type Response2 struct {
    Page   int      `json:"omitempty"`
    Fruits []string `json:"fruits"`
}
```
