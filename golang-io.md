# GOLANG IO

## io.Reader from Bytes
easily implement io.Reader for a buffer
[link](https://golang.org/pkg/bytes/#NewReader)
```golang
buf []byte
newReader := bytes.NewReader(buf)
```
