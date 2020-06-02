# GOLANG FILES

## Summary

Notes on reading and writing files with golang

## Resources

- [Go io Docs](https://golang.org/pkg/io)
- [Linux Process and Threads Don't Mix](https://news.ycombinator.com/item?id=14470231)

### Read Entire File

```golang
func main() {
	r := strings.NewReader("some io.Reader stream to be read\n")

	buf := make([]byte, 4)
	if _, err := io.ReadFull(r, buf); err != nil {
		log.Fatal(err)
	}

	// minimal read size bigger than io.Reader stream
	longBuf := make([]byte, 64)
	if _, err := io.ReadFull(r, longBuf); err != nil {
		fmt.Println("error:", err)
	}
}
```

### Write Fprintf Output To File

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

### Open File With Read And Write Access

often causes 'bad file descriptor' error if you try and read from a write only
file descriptor

```golang
f, err := os.OpenFile(fpath, os.O_RDWR, 0755)
```
