# AWS CLOUDWATCH INSIGHTS Query Examples

## Summary

Example queries for cloudwatch logs insights

## Filter To Discovered Property

AppSync RequestMapping and ResponseMapping logs

```
fields @timestamp, @message
| filter logType like /(?i)(Mapping)/
| limit 2000
```

## Count Of SQS MesageIds Written By Lambda Per Hour

```
fields @message
| filter ispresent(MessageId)
| stats count(MessageId) as Counter by bin(1h)
| sort @timestamp desc
| limit 20
```

## Filter To Web UnAuth Role CognitoIdentity

```
fields @timestamp, @message
| filter userIdentity.arn like /(?i)(arn:aws:sts::111111111111:assumed-role\/myrole-unauth\/CognitoIdentityCredentials)/
| sort @timestamp desc
| limit 200
```

## Get Distinct List Of Events

```
stats count(*) by eventSource
| sort eventSource asc
| limit 2000
```

## Find Lambdas with Errors

```
filter @message like /(?i)(Exception|error|fail)/| fields @timestamp, @message | sort @timestamp desc | limit 20
```

## Parse Inner JSON Fields

```
parse @message "user=*, method:*, latency := *" as @user,
    @method, @latency | stats avg(@latency) by @method,
    @user
```
