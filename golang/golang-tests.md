# GOLANG TESTS

## Summary

Notes on writing tests in golang

## Resources

- [Table Driven Tests](https://dave.cheney.net/2019/05/07/prefer-table-driven-tests)
- [Go Test Tips From Splice](https://splice.com/blog/lesser-known-features-go-test/)

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

## Fail Fast

```console
go test -v -timeout 20m -failfast
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

## Test Helper

- [Golang.org](https://blog.golang.org/go1.9)

```golang
package p

import "testing"

func failure(t *testing.T) {
    t.Helper() // This call silences this function in error reports.
    t.Fatal("failure")
}

func Test(t *testing.T) {
    failure(t)
}
```
