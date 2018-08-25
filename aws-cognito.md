# AWS COGNITO

## Identity Pool Setup
- create identity pool
- create authorized and unauthorized roles, with policies and trusts

## User Pool Setup
- create sms role if you want sms
- if using email, create SES verified identity. Log in to email to verify

## Basic Unauthorized Role Policy
```
{
	"Version": "2012-10-17",
		"Statement": [
			{
				"Effect": "Allow",
				"Action": [
					"mobileanalytics:PutEvents",
				"cognito-sync:*"
				],
				"Resource": [
					"*"
				]
			}
		]
}
```

## Basic Unauthorized Role Trust Relationship
```
{
	"Version": "2012-10-17",
		"Statement": [
		{
			"Effect": "Allow",
			"Principal": {
				"Federated": "cognito-identity.amazonaws.com"
			},
			"Action": "sts:AssumeRoleWithWebIdentity",
			"Condition": {
				"StringEquals": {
					"cognito-identity.amazonaws.com:aud": "us-west-2:eeeeeeee-eeee-eeee-eeee-eeeeeeeeeeee"
				},
				"ForAnyValue:StringLike": {
					"cognito-identity.amazonaws.com:amr": "unauthenticated"
				}
			}
		}
		]
}
```

## Basic Authorized Role Policy
```
{
	"Version": "2012-10-17",
		"Statement": [
		{
			"Effect": "Allow",
			"Action": [
				"mobileanalytics:PutEvents",
			"cognito-sync:*",
			"cognito-identity:*"
			],
			"Resource": [
				"*"
			]
		}
		]
}
```

## Basic Unauthorized Role Trust Relationship
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "cognito-identity.amazonaws.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "cognito-identity.amazonaws.com:aud": "us-west-2:eeeeeeee-eeee-eeee-eeee-eeeeeeeeeeee"
        },
        "ForAnyValue:StringLike": {
          "cognito-identity.amazonaws.com:amr": "authenticated"
        }
      }
    }
  ]
}
```
