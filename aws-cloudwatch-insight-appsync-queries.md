# AWS CLOUDWATCH INSIGHT APPSYNC QUERIES

## Summary

Saved queries for reuse on cloudwatch insight

## Filter By Field Name And Mapping

```
fields @timestamp, logType, fieldName, functionName, @message
| filter fieldName like /(?i)(myFieldName)/
| filter logType like /(?i)(Mapping)/
| sort @timestamp desc
| limit 200
```

## Filter By Function Name

```
fields @timestamp, logType, fieldName, functionName, @message
| filter functionName like /(?i)(myFunctionName)/
| sort @timestamp desc
| limit 200
```
