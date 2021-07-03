# GOLANG JSON

## Summary

Notes on working with JSON in golang

## Resources

- [Online JSON to Go Generator](https://mholt.github.io/json-to-go/)
- [JSON Code Generator Online Tool](https://app.quicktype.io/)
- [Dyamic JSON in Go](https://eagain.net/articles/go-dynamic-json/)

## Convert JSON to GO Struct

- [JSON-to-Go](https://mholt.github.io/json-to-go/)

## Parse JSON To Interface

```golang
var res interface{}
err := json.Unmarshal([]byte("mybites"), &res)
```

## Parse Golang Back To JSON

```golang
spec, err := json.Marshal(chain)
```

## Parse Struct / Interface To Escaped Stringified JSON

## Omit Field If Empty

```golang
type Response2 struct {
    Page   int      `json:"page,omitempty"`
    Fruits []string `json:"fruits"`
}
```

## Marshal String Escaped JSON

- [SO](https://stackoverflow.com/questions/16846553/how-to-unmarshal-an-escaped-json-string-in-go/38684420)
- [Go Playground](http://play.golang.org/p/id4f4r9tEr)

use `strconv.Unquote()` first

## Use GJSON Package

```golang
package main

import "github.com/tidwall/gjson"

const json = `{"name":{"first":"Janet","last":"Prichard"},"age":47}`

func main() {
	value := gjson.Get(json, "name.last")
	println(value.String())
}
```

## Example Interfaces And JSON

#### Map of String Interface

```json
{
  "payload": {
    "item": "shirt",
    "orderType": "air"
  }
}
```

```golang
res := map[string]interface{}{"payload": map[string]interface{}{"item": "shirt", "orderType": "air"}}
```

#### Array Of Objects

```json
{
  "payload": [
    {
      "item": "shirt",
      "orderType": "air"
    }
  ]
}
```

```golang
res := map[string]interface{}{"payload": []map[string]interface{}{map[string]interface{}{"item": "shirt", "orderType": "air"}}}
```

#### Interpolate String

```golang
var payload = []byte(fmt.Sprintf(`{"foo":%q, "hello":%q}`, val1, val2))
```
