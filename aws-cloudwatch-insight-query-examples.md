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
