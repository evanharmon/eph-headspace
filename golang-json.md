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
    Page   int      `json:"page,omitempty"`
    Fruits []string `json:"fruits"`
}
```

## Marshal String Escaped JSON

[SO](https://stackoverflow.com/questions/16846553/how-to-unmarshal-an-escaped-json-string-in-go/38684420)
[Go Playground](http://play.golang.org/p/id4f4r9tEr)

use `strconv.Unquote()` first
