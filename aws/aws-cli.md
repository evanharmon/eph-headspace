# AWS CLI

## Summary

Notes on working with the AWS cli

## Resources

- [Install V2 CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

## V1 CLI INSTALL

### Install macOS

```console
brew install awscli
```

### Update

```console
pip install --upgrade --user awscli
```

#### Fix Bad Interpreter Error

```console
brew reinstall awscli
brew link --overwrite awscli
```

### CLI Shell Variables

```console
export AWS_DEFAULT_PROFILE='hss-dev'
export AWS_DEFAULT_REGION='us-east-1'
export AWS_DEFAULT_OUTPUT='json'
```

### Check Current Profile

```console
aws configure list
```

#### Quick Way To Get Account ID

```console
aws sts get-caller-identity --query Account --output text
```

## Clear CLI Cache

```console
rm -rf ~/.aws/cli/cache/*
```
