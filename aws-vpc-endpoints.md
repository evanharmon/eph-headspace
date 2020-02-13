# AWS VPC ENDPOINTS

## Summary

Notes on setting up and using VPC Endpoints

## Resources

- [Setting Up ECS / ECR / S3 VPC Endpoints](https://aws.amazon.com/blogs/compute/setting-up-aws-privatelink-for-amazon-ecs-and-amazon-ecr/)

## Creation With Restricted Policy

create a policy limiting it to just your AWS account

```json
{
  "Version": "2012-10-17",
  "Id": "S3-Account-Permissions",
  "Statement": [
    {
      "Sid": "1",
      "Effect": "Allow",
      "Principal": { "AWS": ["arn:aws:iam::ACCOUNT-ID-WITHOUT-HYPHENS:root"] },
      "Action": "s3:*",
      "Resource": ["arn:aws:s3:::mybucket", "arn:aws:s3:::mybucket/*"]
    }
  ]
}
```

## VPN Acccess

Doesn't look like VPC endpoints can be used to provide VPN access to services like S3
[Reddit](https://www.reddit.com/r/aws/comments/4fzrts/route_s3_traffic_through_vpn/_)
[SO](https://stackoverflow.com/questions/1764988/amazon-s3-over-vpn#46740474)
