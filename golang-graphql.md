# GOLANG GRAPHQL

## Summary

Notes on working with graphql in Golang

## Resources

- [Example Custom Client](https://gist.github.com/lox/d97691970dbcc666b07b3d858a6fbb95)
- [Custom Unmarshalling](https://blog.gopheracademy.com/advent-2017/custom-json-unmarshaler-for-graphql-client/)

## Parse GraphQL Response JSON

- [Playground](https://goplay.space/#9fH_1_VTN9r)

```golang
package main

import (
	"encoding/json"
	"fmt"
	"log"
)

type graphQLError struct {
	Message string
}

type graphQLResponse struct {
	Data   interface{}
	Errors []graphQLError
}

func main() {

	response := &graphQLResponse{
		Data:   map[string]interface{}{"item": "shirt", "orderType": "air"},
		Errors: []graphQLError{graphQLError{Message: "error test"}},
	}
	fmt.Printf("response %+v\n", response)

	s, err := json.Marshal(response)
	if err != nil {
		log.Fatal(err)
	}

	fmt.Printf("\n stringified %s", string(s))
}
```
