# GOLANG REFLECT

## Summary

Notes on using the reflect package in golang

## Iterate Through Struct Field Names And Values

[Playground](http://play.golang.org/p/gSnZ8mLll-)

```golang
x := struct {
  Foo string
  Bar int
}{"foo", 2}

v := reflect.ValueOf(x)

values := make([]interface{}, v.NumField())

for i := 0; i < v.NumField(); i++ {
  fmt.Printf("Field Name: %v\n", v.Type().Field(i).Name)
  fmt.Printf("Field Value: %v\n", v.Field(i).Interface())
  values[i] = v.Field(i).Interface()
}

fmt.Println(values)
```

```golang
func validateConfig(cfg interface{}) (err error) {
    v := reflect.ValueOf(cfg)

    for i := 0; i < v.NumField(); i++ {
    •   if s := v.Field(i).Interface(); s == "" {
    •   •   return fmt.Errorf("%s should not be an empty string", v.Type().Field(i).Name)
    •   }
    }

    return nil
}
```
