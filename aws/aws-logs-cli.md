# AWS LOGS CLI

## Summary

Notes on using the aws logs cli command to get log data from Cloudwatch

## Get Log Group Names Easily

```console
aws logs describe-log-groups --log-group-name-prefix "/aws/appsync/"
```

## Get Log Streams Easily

```console
aws logs describe-log-streams --log-group-name /aws/appsync/apis/aaaaaaaaaaaaaaaaaaaaaaaaaa --log-stream-name-prefix 444444
```
