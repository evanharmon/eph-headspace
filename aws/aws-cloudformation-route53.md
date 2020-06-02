# AWS CLOUDFORMATION ROUTE 53

## Alias Record For S3 Bucket
DNSName is the s3 region endpoint
```
wwwRecordSet:
  Type: AWS::Route53::RecordSet
  Properties:
    Name: www.dianabresson.com.
    Type: A
    HostedZoneName: dianabresson.com.
    AliasTarget:
      HostedZoneId: !Ref PublicHostedZone
      DNSName: s3-website-us-west-2.amazonaws.com
```
