# AWS SDK GOLANG

## Summary

Notes on working with the v2 AWS sdk for golang

## Resources

[Go Docs](https://godoc.org/github.com/aws/aws-sdk-go-v2)

## Mock Credentials Provider

Avoids other sdk calls complaining about configuration or missing keys for
`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`, `AWS_SESSION_TOKEN`, etc

```golang
cfg.Credentials = aws.NewStaticCredentialsProvider("AKID", "SECRET", "SESSION")
region := "us-east-1"
cfg.Region = region
svc, err := MyNewService(serviceURL, cfg.Credentials)
```
