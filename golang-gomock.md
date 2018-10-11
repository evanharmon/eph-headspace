# GOLANG GOMOCK
[GITHUB](https://github.com/golang/mock)

## Mock Listed Interfaces
```console
mockgen \
    github.com/evanharmon/eph-music-micro/storage/proto/storagepb \
    StorageClient,Storage_UploadFileClient \
    > proto/mock_storagepb/storage_mock.go
```

## Mock Specific Files
```console
mockgen \
    -source core/server.go \
    -destination core/mock_server/mock_server.go
```

## Gomock Not Used Error
remember to create interfaces for Gomock to use in your file
```golang
type Service interface {
	NewServerGRPC(cfg ServerGRPCConfig) (*ServerGRPC, error)
	Listen() error
	Close()
}
```

## Custom Mock Interface Names
```console
	mockgen \
      -mock_names Service=MockClientGRPC \
      -source core/client.go \
      -destination core/mock_client/mock_client.go
```
