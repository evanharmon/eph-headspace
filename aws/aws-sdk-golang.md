# AWS SDK GOLANG

## Summary

Notes on working with the v2 AWS sdk for golang

## Resources

- [SDK v2 Go Docs](https://godoc.org/github.com/aws/aws-sdk-go-v2)
- [SDK v1 Mock S3](https://golangcode.com/mocking-s3-upload/)
- [SDK v2 Mock S3Manager](https://stackoverflow.com/questions/49742700/have-a-go-function-accept-different-structs-as-input-with-methods)

### Mock Credentials Provider

Avoids other sdk calls complaining about configuration or missing keys for
`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_SESSION_TOKEN`, etc

```golang
cfg.Credentials = aws.NewStaticCredentialsProvider("AKID", "SECRET", "SESSION")
region := "us-east-1"
cfg.Region = region
svc, err := MyNewService(serviceURL, cfg.Credentials)
```
