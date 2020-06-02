# AWS ROUTE 53

## Summary

Notes on using Route53

## Best Practice For Testing

Buy a throwaway domain for testing that is owned / managed by one of your AWS
accounts. Using these domains in test setups avoids having to make multiple
requests to other groups / IT for dns work, etc.

## Limitations

50 Domains per AWS account - request for higher limit

## Load Balancers

ELB's don't have a pre-defined IPv4 address. You resolve them using a DNS name
You can use Route53 for private cloud/vpn routing as well

## CNAME is a resource record in DNS that points to another domain name

Ex. bar.example.com to foo.example.com foo.example.com is the CNAME
You can't use a cname on a naked domain name

## Alias

used to map
given a choice, it's almost always better to use an Alias not a CNAME

## Alias record to s3 buckets

S3 bucket name must match the A record EXACTLY
`www.mydomain.com`
`http://www.mydomain.com.s3-website-us-west-2.amazonaws.com`

## MX Records

Do Not Use Any Prefixes In Name
Name field must be left completely blank - so it's a naked domain with MX Records
mx.mydomain.com with MX records will fail
