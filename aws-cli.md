# AWS CLI

# Install AWS CLI

```console
brew install awscli
```

# Update AWS CLI

```console
pip install --upgrade --user awscli
```

# CLI Shell Variables

```console
export AWS_DEFAULT_PROFILE='hss-dev'
export AWS_DEFAULT_REGION='us-east-1'
export AWS_DEFAULT_OUTPUT='json'
```

# Check Current Profile

```console
aws configure list
```

# Set Up Role Switching

Edit config file to add new profile for role

```
[profile hss-prod]
role_arn = arn:aws:iam::prodaccount#:role/rolename
source_profile = hss-dev
mfa_serial = arn:aws:iam::devaccount#:mfa/username
```

# Configure mfa session token

(https://aws.amazon.com/premiumsupport/knowledge-center/authenticate-mfa-cli/)

```console
aws sts get-session-token \
  --serial-number arn-of-the-mfa-device \
  --token-code code-from-token
```

# Set ENV Variable From Get-Session-Token

```console
export AWS_SESSION_TOKEN="$(aws sts get-session-token | jq '.Credentials.SessionToken')"
```

## Quick Way To Get Account ID

```console
aws sts get-caller-identity --query Account --output text
```
