# AWS IAM POLICY EXAMPLE
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Resource": [
                "arn:aws:logs:us-west-2:695616613592:log-group:/aws/codebuild/www-dev",
                "arn:aws:logs:us-west-2:695616613592:log-group:/aws/codebuild/www-dev:*"
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
                "arn:aws:s3:::dianabresson-test-site/*"
            ],
            "Action": [
                "s3:PutObject"
            ]
        }
    ]
}
```
