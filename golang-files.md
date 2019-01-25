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
