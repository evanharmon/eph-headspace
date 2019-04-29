# AWS CLOUDFRONT

- like a CDN, serves to users based on their IP region
- supports an entire website: dynamic, static, streaming, interactive content

## Resources

[Namecheap, Route53, S3, Cloudfront Guide](https://benjamincongdon.me/blog/2017/06/13/How-to-Deploy-a-Secure-Static-Site-to-AWS-with-S3-and-CloudFront/)

## Possible Origins

Supports non-AWS origin servers through Route 53
Distinguishes between multiple origins in the same distribution
Origin ID Must be Unique

- S3
- EC2
- ELB
- Route 53

## Edge Locations

- location where content will be cached, separate from AWS Region / AZ
- can write / PUT an object
- requests automatically routed to nearest edge location
- time to live (TTL) in seconds used to limit lifecyle

## Distribution

collection of Edge Locations

## Cache

can be cleared but you are charged for the action

## Allowed HTTP Methods

PUT, POST, PATCH, DELETE

## Path Pattern

Uses RegEx

## Restricting Access

can use signed URLs or signed cookies

## Web Application Firewall (WAF)

can use web application firewall ACL

## Alternate CNAMES

example cdn.harmonsoftwaresolutions.com
If using Alternate CNAMES, you have to upload your own SSL certificate

## Invalidations

A way to remove objects from the CDN but you pay for it

## Grant Read Permissions On Bucket

If yes, updates the S3 files in the new CDN bucket to have read access

## S3 Logging Bucket Settings

Encryption must be AES-256. KMS will prevent Cloudfront from writing any logs to the s3 bucket

## Unzip Logs

```console
gzip -d 11111111111111.2019-04-25-13.eeeeeeee.gz
```
