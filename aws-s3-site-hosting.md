# AWS S3 SITE HOSTING

## Bucket policy for public read access
Fixes 403 forbidden / access denied errors
```
{
  "Version": "2012-10-17",
  "Statement": [
  {
  "Effect": "Allow",
  "Resource": [
  "arn:aws:logs:us-east-1:111111111111:log-group:/aws/codebuild/www-dev",
  "arn:aws:logs:us-east-1:111111111111:log-group:/aws/codebuild/www-dev:*"
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
  "arn:aws:s3:::codepipeline-us-east-1-*"
  ],
  "Action": [
  "s3:PutObject",
  "s3:GetObject",
  "s3:GetObjectVersion"
  ]
  },
  {
  "Effect": "Allow",
  "Action": [
  "ssm:GetParameters"
  ],
  "Resource": "arn:aws:ssm:us-east-1:111111111111:parameter/CodeBuild/*"
  },
  {
  "Effect": "Allow",
  "Resource": [
  "arn:aws:s3:::www.harmonsoftwaresolutions.com-artifacts/*",
  "arn:aws:s3:::www.harmonsoftwaresolutions.com/*"
  ],
  "Action": [
  "s3:PutObject",
  "s3:DeleteObject"
  ]
  }
  ]
}
```
