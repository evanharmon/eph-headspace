# AWS CODE BUILD IAM

## Troubleshooting
### Access Denied On S3
add your s3 bucket for artifacts
add build folder
```javascript
{
  "Version": "2012-10-17",
    "Statement": [
    {
      "Effect": "Allow",
      "Resource": [
        "arn:aws:logs:us-west-2:111111111111:log-group:/aws/codebuild/my-bucket",
        "arn:aws:logs:us-west-2:111111111111:log-group:/aws/codebuild/my-bucket:*"
      ],
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents"
      ]
    },
    {
      "Effect": "Allow",
      "Resource": [ "arn:aws:s3:::codepipeline-us-east-1-*" ],
      "Action": [
        "s3:PutObject",
        "s3:GetObject",
        "s3:GetObjectVersion"
      ]
    },
    {
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::my-artifacts-bucket/*",
        "arn:aws:s3:::my-www-bucket/*"
      ],
      "Action": [ "s3:PutObject" ]
    }
  ]
}
```
