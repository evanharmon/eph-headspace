# AWS VAULT

## Summary

Notes on using the aws-vault cli tool

## Resources

- [Github](https://github.com/99designs/aws-vault)
- [CloudPosse Linux Setup](https://docs.cloudposse.com/tools/aws-vault/)

## Installation

### macOS Install

```console
brew cask install aws-vault
```

## Profiles

### List Profiles

```console
aws-vault list
```

### Add Existing AWS-CLI Profile

Access Key ID and Secret Key will have to be entered again

OS X Keychain

```console
aws-vault add --keychain="aws-vault" default
```

### Add MFA AWS-CLI Profile

Don't need to be added, just run an exec command and MFA input will pop up:

```console
aws-vault exec mycrossaccount -- aws s3 ls
```

## Commands

### Execute AWS Command Using Temporary Creds

```console
aws-vault exec <profile> -- aws s3 ls
```

### Remove Sessions

```console
aws-vault remove dev --sessions-only
```
