# AWS SDK GOLANG SQS

## Summary

Notes on working with the v2 AWS sdk for golang and SQS

## Resources

[Go Docs](https://godoc.org/github.com/aws/aws-sdk-go-v2/service/sqs)
[Customize Endpoing for Localstack](https://docs.aws.amazon.com/sdk-for-go/api/aws/endpoints/)

## Use Localstack

[Godoc](https://godoc.org/github.com/aws/aws-sdk-go-v2/aws#EndpointResolver)

```golang
defaultResolver := endpoints.NewDefaultResolver()
cfg, err := external.LoadDefaultAWSConfig()
if err != nil {
    log.Fatalf("Failed to configure AWS SDK %v.", err)
}

cfg.Region = "us-east-1"
localStackResolver := func(service, region string) (aws.Endpoint, error) {
    if service == sqs.EndpointsID {
        return aws.Endpoint{
            URL:           "localstack:31000",
            SigningRegion: "us-east-1",
        }, nil
    }

    return defaultResolver.ResolveEndpoint(service, region)
}
cfg.EndpointResolver = aws.EndpointResolverFunc(localStackResolver)

// SQS POLLER
sqsClient := sqs.New(cfg)
```
