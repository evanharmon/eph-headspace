# AWS CODE BUILD IAM

## Troubleshooting
### Access Denied On S3
add your s3 bucket for artifacts
add build folder
```
{
  "Version": "2012-10-17",
    "Statement": [
    {
      "Effect": "Allow",
      "Resource": [
        "arn:aws:logs:us-west-2:111111111111:log-group:/aws/codebuild/www-prod",
      "arn:aws:logs:us-west-2:111111111111:log-group:/aws/codebuild/www-prod:*"
      ],
      "Action": [
        "logs:CreateLogGroup",
      "logs:CreateLogStream",
      "logs:PutLogEvents"
      ]
    },
    {
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::codepipeline-us-west-2-*"
      ],
      "Action": [
        "s3:PutObject",
      "s3:GetObject",
      "s3:GetObjectVersion"
      ]
    },
    {
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::dianabresson-www-prod-artifacts/*",
      "arn:aws:s3:::dianabresson-www-prod/*"
      ],
      "Action": [
        "s3:PutObject"
      ]
    }
  ]
}
```
