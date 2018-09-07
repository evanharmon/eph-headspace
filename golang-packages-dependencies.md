# GOLAND PACKAGES - DEPENDENCIES

## Install All Dependencies
```console
$ go get -d ./...
```

## Install Dependencies Just For Repo
```console
$ go get -d .
```

## Init And Unused Packages
unused packages should be prepended with `_`. Any `init()` functions will be run
within the package imported before `main()`
```golang
import _ "packagename"
```
