# GOLANG PROTOBUF
[](https://github.com/golang/protobuf)

## Install
```console
$ go get -u github.com/golang/protobuf/protoc-gen-go
```

## Nest Protobuf References
```golang
&pb.UploadFileRequest{Chunk: &pb.Chunk{Content: buf[:n]}}
```
