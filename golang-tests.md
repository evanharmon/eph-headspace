# GOLANG TESTS

All golang variables are initialized to their respective zero values

## Run A Single Test Function

```golang
func getProjectID() { ... }
```

```console
go test -run GetProjectID
```

## Run All Tests In Project

```console
go test ./...
```

## Ignore Package

```console
go test `go list ./... | grep -v 'testhelper'`
```

## Check Code Coverage

```console
go test --cover
```

## Run Tests As Package User

Use `*_test` package doesn’t allow unexported identifiers

## Separate Out Integration Tests

name the file `storage_integration_test.go`

add tag to first line of file and test file

```golang
// +build integration

// Package ...
package mypkg
```

run tests with tag

```console
go test --tags=integration
```
