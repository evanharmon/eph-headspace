# GOLANG APPEND

## Append Streamed Chunks
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

## Append Key / Value (Property) To map[string]interface{}
Don't need Append!
```golang
input := map[string]interface{}{"processor_type": "debugger"}
input["name"] = "DeBugger1"
  ```
