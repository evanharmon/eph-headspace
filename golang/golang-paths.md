# GOLANG PATHS

## Summary

Notes on using paths with go. Includes notes on filepaths

## Get Absolute Path From Relative Path

[SO](https://stackoverflow.com/questions/47261719/how-can-i-resolve-a-relative-path-to-absolute-path-in-golang)

```golang
base := "/home/bob"
fmt.Println(path.Join(base, "work/go", "src/github.com"))
```

## Get Filename Without Extension

[Github](https://siongui.github.io/2018/02/25/go-get-file-name-without-extension/)

```golang
func FilenameWithoutExtension(fn string) string {
      return strings.TrimSuffix(fn, path.Ext(fn))
}
```

## Get Directory From Filepath

```golang
dir, fname := path.Split(keyPath)
```

## Split FileName And Directory

```golang
dir, file := filepath.Split(fpath)
```

## Create All Subdirectories

```golang
err := os.MkdirAll("dirname", 0700)
```

## Test Path

```golang
startPath != path.Match(key, fmt.Sprintf("%s/%s"))
```
