# AWS SAM CLI

## Summary

Notes on using the AWS `sam` cli

## Install

Requires Python 2.7, 3.6, or 3.7

```console
pip install --user aws-sam-cli
```

## USAGE

#### Generate Local Event Payloads

[AWS](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-local-generate-event.html)

```console
sam local generate-event s3 put
```

#### Invoke Lambda

```console
sam local invoke --event testdata/events/s3-put.json
```

## Common Errors

#### Error: Read Only Container On Local Invoke

`/var/task:ro inside runtime container`

do file operations to `/tmp` instead
