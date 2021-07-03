# GOLANG IO

## Summary

Notes on reading and writing using the `io` package in golang

## io.Reader from Bytes

easily implement io.Reader for a buffer

- [link](https://golang.org/pkg/bytes/#NewReader)

```golang
buf []byte
newReader := bytes.NewReader(buf)
```

## Write And Seek Example

- [hotexamples](https://golang.hotexamples.com/examples/io/WriteSeeker/-/golang-writeseeker-class-examples.html)

```golang
func writeAt(w io.WriteSeeker, c int64, p []byte) (int64, error) {
	if _, err := w.Seek(c, 0); err != nil {
		return 0, err
	}
	n, err := w.Write(p)
	return int64(n), err
}
```
