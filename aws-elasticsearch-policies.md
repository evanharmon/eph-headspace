# AWS ELASTIC SEARCH POLICIES

## Access Control
(https://blogs.aws.amazon.com/security/post/Tx3VP208IBVASUQ/How-to-Control-Access-to-Your-Amazon-Elasticsearch-Service-Domain)

### Policy for specific IP access
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "AWS": "*"
      },
      "Action": "es:*",
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": [
            "208.108.88.0/24"
          ]
        }
      },
      "Resource": "arn:aws:es:us-east-1:111111111111:domain/delete-this/*"
    }
  ]
}

### Identity-based Policy ESADMIN
```
{
  "Version": "2012-10-17",
  "Statement": [{
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::111111111111:user/recipes1alloweduser"
      },
      "Action": "es:*",
      "Resource": "arn:aws:es:us-west-2:111111111111:domain/recipes1/*"
    }
  ]
}
```

## Power User Policy
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Resource": "arn:aws:es:us-west-2:111111111111:domain/*",
      "Action": ["es:*"],
      "Effect": "Allow"
    },
    {
      "Resource": "arn:aws:es:us-west-2:111111111111:domain/*",
      "Action": ["es: DeleteElasticsearchDomain",
                  "es: CreateElasticsearchDomain"],
      "Effect": "Deny"
    }
  ],
}
```

# Analytics Viewer Policy
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Resource":
        "arn:aws:es:us-west-2:111111111111:domain/recipes1/analytics",
      "Action": ["es:ESHttpGet"],
      "Effect": "Allow"
    }
  ],
}
```
