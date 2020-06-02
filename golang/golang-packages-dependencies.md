# GOLANG PACKAGES - DEPENDENCIES

## File / Folder Placement
- cannot have multiple package names inside one folder
- cannot have a package name spread across multiple folders

## Naming Conventions
- short, concise, lowercase names
- doesn't have to be unique name

## Use Packages With The Same Name
ok to have packages with the same name. Use a named import
```golang
import (
  "cloud.google.com/go/storage"
  myStorage "github.com/evanharmon/eph-music/storage"
  )
```

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
