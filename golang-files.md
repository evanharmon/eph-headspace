# GOLANG FILES

## Summary

Notes on reading and writing files with golang

## Resources

- [Linux Process and Threads Don't Mix](https://news.ycombinator.com/item?id=14470231)

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

## Open File With Read And Write Access

often causes 'bad file descriptor' error if you try and read from a write only
file descriptor

```golang
f, err := os.OpenFile(fpath, os.O_RDWR, 0755)
```
