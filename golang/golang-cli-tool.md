# GOLANG CLI TOOL

## File And Folders Ignored
any folder starting with a `.` or `_` is ignored
any folder named `testdata`

## Clean Out Executable Before Git Commit
```console
$ go clean .
```

## Build Every Package In A Folder
use `...`
```console
go build github.com/evanharmon/eph-music/...
```

## Traverse Directory Tree And Build
```console
$ go build .
```

## Working Directory
go cli tool references the directory of the package.
You can use `testdata/mock.json` and not have to run the go tool from the
package directory
