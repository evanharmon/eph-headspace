# GOLANG TROUBLESHOOTING

## {Variable} Is Not An Expression
### Trying to assign with reflect.TypeOf?
```golang
// ERRORS
// s1 := Session
// fmt.Println(reflect.TypeOf(s1))

s2 := Session{}
fmt.Println(reflect.TypeOf(s2))
```
