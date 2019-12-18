# AWS S3 SELECT

## Summary

Notes on using s3 select to grab object content

## Resources

- [AWS CLI DOCS](https://docs.aws.amazon.com/cli/latest/reference/s3api/select-object-content.html)
- [AWS Query Docs](https://docs.aws.amazon.com/AmazonS3/latest/dev/s3-glacier-select-sql-reference-select.html)
- [AWS General Reference](https://docs.aws.amazon.com/AmazonS3/latest/API/API_SelectObjectContent.html)

## Example CLI JSON Query

```console
aws s3api select-object-content \
  --bucket bucket \
  --key large-file.json \
  --expression-type SQL \
  --expression "SELECT * FROM S3Object LIMIT 1000 OFFSET 1000" \
  --input-serialization '{"JSON": {"Type": "LINES"}}' \
  --output-serialization '{"JSON": {}}' \
  --out-file out.txt
```
