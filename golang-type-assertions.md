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
