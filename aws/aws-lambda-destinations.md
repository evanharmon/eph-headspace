# AWS LAMBDA DESTINATIONS

## Summary

Compute service

## Resources

- [AWS Blog](https://aws.amazon.com/blogs/compute/introducing-aws-lambda-destinations/)
- [Trek10 Guide](https://www.trek10.com/blog/lambda-destinations-what-we-learned-the-hard-way)

## Common Mistakes

Cannot test destination via AWS Console! It's not an async invocation

## Invoke From CLI

```console
aws lambda invoke \
  --function-name test-destinations \
  --invocation-type Event \
  --payload file://payload.json \
  --cli-binary-format raw-in-base64-out \
  response.json
```
