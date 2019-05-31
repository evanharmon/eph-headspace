# GOLANG FILES

## Summary

Notes on reading and writing files with golang

## Write Fprintf Output To File

```golang
f, err := os.Create("/tmp/myfile")
if err != nil {
  panic(err)
}
defer f.Close()
mystr := "test"
w := bufio.NewWriter(f)
_, err = fmt.Fprintf(w, "%v\n", mystr)
if err != nil {
  panic(err)
}
w.Flush()
```

## Get Filename Without Extension

[Github](https://siongui.github.io/2018/02/25/go-get-file-name-without-extension/)

```golang
func FilenameWithoutExtension(fn string) string {
      return strings.TrimSuffix(fn, path.Ext(fn))
}
```

## Split FileName And Directory

```golang
dir, file := filepath.Split(fpath)
```

## Open File With Read And Write Access

often causes 'bad file descriptor' error if you try and read from a write only
file descriptor

```golang
f, err := os.OpenFile(fpath, os.O_RDWR, 0755)
```
