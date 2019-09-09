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
