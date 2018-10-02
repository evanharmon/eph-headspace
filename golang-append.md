# GOLANG APPEND

## Append Stramed Chunks
```golang
content = []byte
for {
  chunk, err := stream.Recv()
  if err != nil {
    if err == io.EOF {
      return content
    }

    return err
  }
  content = append(content, chunk...)
}
```
