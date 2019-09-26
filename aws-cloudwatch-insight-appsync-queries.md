# AWS CLOUDWATCH INSIGHT APPSYNC QUERIES

## Summary

Saved queries for reuse on cloudwatch insight

## Filter By Function Name And Mapping

```
fields @timestamp, functionName, @message
| filter fieldName like /(?i)(myFunctionName)/
| filter logType like /(?i)(Mapping)/
| sort @timestamp desc
| limit 200
```
