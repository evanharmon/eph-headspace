# GOLANG TYPE ASSERTIONS

## Get Type
"reflect"
`fmt.Printf(reflect.TypeOf(variable))`

## Assert A Map
`myURL["local"].(string)`

## Catch Type Assertion Errors
```golang
s, ok := someData.([]string)
if !ok {
  log.Printf("got data of type %T but wanted []string", someData)
}
```
... handle the failure somehow

## Assert interface {}([]interface {})
```golang
choose.([]interface{})[0]
```

## Assert interface {}(map[string]interface {})
```golang
chooser.(map[string]interface{})
```
same as
```golang
chooser.(interface{}).(map[string]interface{})
```

## Get String From Array Of Objects - map[string]interface{}
example json: `[{ "type": "lpf" }]`
```golang
parsed, ok := proc["type"].(string)
```
parsed == "lpf"

## Nest JSON
```golang
// Package main provides ...
package main

import (
	"encoding/json"
	"fmt"
)

func main() {
	// create unmarshal'd representation of data
	var res interface{}
	res = map[string]interface{}{"payload": map[string]interface{}{"item": "shirt", "orderType": "air"}}
	fmt.Printf("res %v\n", res)

	// parse and save payload data
	var payload interface{}
	payload = res.(map[string]interface{})["payload"]
	fmt.Printf("payload %v\n", payload)

	// create dBlock with nested parsed payload inside it
	var dBlock interface{}
	dBlock = map[string]interface{}{"d": payload}

	// build final object
	var result interface{}
	result = map[string]interface{}{"payload": dBlock}
	fmt.Printf("result %v\n", result)

	// Marshal back to json buffer
	j, err := json.Marshal(result)
	if err != nil {
		fmt.Printf("error %v\n", err)
	}

	// convert to string
	str := string(j)
	fmt.Printf("str %v\n", str)
}
```
