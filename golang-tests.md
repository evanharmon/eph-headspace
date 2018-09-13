# GOLANG TESTS
All golang variables are initialized to their respective zero values

## Run A Single Test Function
```golang
func getProjectID() { ... }
```
```console
$ go test -run GetProjectID
```

## Run All Tests In Project
```console
$ go test ./...
```

## Ignore Package
```console
$ go test `go list ./... | grep -v 'testhelper'`
```

## Check Code Coverage
```console
$ go test --cover
```
