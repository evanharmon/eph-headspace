# GOLANG METHOD SETS
[Wiki](https://github.com/golang/go/wiki/MethodSets)
define the rules around interface compliance
define the set of methods for the type

## Method Receiver Values
Receiver type value can only accept values
```golang
func (s Service) myFunc() {}

```
OK: `myFunc(svc)`
NOT OK: `myFunc(&svc)`

## Method Receiver Pointer
Receiver type pointer can accept value or pointer
```golang
func (s *Service) myFunc() {}
```
OK: `myFunc(svc)`
OK: `myFunc(&svc)`
