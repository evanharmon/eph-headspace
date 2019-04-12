# AWS CONFIGURE CLI

## Summary

Notes on using the configure command to interact with shared credential files

## Resources

[Docs](https://docs.aws.amazon.com/cli/latest/reference/configure/index.html#cli-aws-configure)

## Set Config From \$AWS_CONTAINER

```yaml
- >
  curl -qL -o aws_credentials.json
  http://169.254.170.2/$AWS_CONTAINER_CREDENTIALS_RELATIVE_URI >
  aws_credentials.json
- aws configure set region $AWS_REGION
- >
  aws configure set aws_access_key_id
  `/root/bin/jq -r '.AccessKeyId' aws_credentials.json`
- >
  aws configure set aws_secret_access_key
  `/root/bin/jq -r '.SecretAccessKey' aws_credentials.json`
- >
  aws configure set aws_session_token
  `/root/bin/jq -r '.Token' aws_credentials.json`
```

## Set Config From STS ASSUME_ROLE

```yaml
export ROLE_ARN='arn:aws:iam::123456789012:role/myrole'
aws --output json sts assume-role --role-arn $ROLE_ARN --role-session-name role-arn > custom_creds.json
- aws configure set region us-east-1 --profile myprofile
- >
aws configure set aws_access_key_id
`/root/bin/jq -r '.Credentials.AccessKeyId' custom_creds.json` --profile myprofile
- >
aws configure set aws_secret_access_key
`/root/bin/jq -r '.Credentials.SecretAccessKey' custom_creds.json` --profile myprofile
- >
aws configure set aws_session_token
`/root/bin/jq -r '.Credentials.SessionToken' custom_creds.json` --profile myprofile
```

## List Config Location For Profile

```yaml
aws configure list --profile myprofile
```
