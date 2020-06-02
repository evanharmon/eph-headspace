# GOLANG COVERAGE

## Summary

Notes on evaluating code coverage in Golang

## Create Coverage File

```console
go test --coverprofile coveragefile
```

## View Coverage File Analysis

```console
go tool cover -html=coveragefile -o coverage.html
```
