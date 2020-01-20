# AWS CLI

## Summary

Notes on working with the AWS cli

## Resources

# Install

```console
brew install awscli
```

# Update

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

## Quick Way To Get Account ID

```console
aws sts get-caller-identity --query Account --output text
```
