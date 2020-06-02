# GOLANG MODULES

## Summary

Working with golag modules

## Resources

[Using Go Modules](https://blog.golang.org/using-go-modules)

## GO MOD INIT

only run `go mod init` in the root directory of the repo

## Clean Up Unused Dependencies

```console
go mod tidy
```

## Go Module Cache Location

Typically at `$GOPATH/pkg/mod`. Can check with the below command:

```console
go mod download -json
```

## Print Module Dependency Graph

```console
go mod graph
```

## Speed Up Docker Local Go Mod Builds

```
COPY ./go.mod .
RUN go mod download
```

## Vendoring

#### Init Vendor Modules

```console
go mod vendor
```

### Use Vendor Modules

```console
go build -mod vendor
go install -mod vendor
go test -mod vendor
```
