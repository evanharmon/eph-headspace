# AWS CLOUDWATCH INSIGHT APPSYNC QUERIES

## Summary

Saved queries for reuse on cloudwatch insight

## Resources

- [Example AWS Blog Appsync CW Insight Queries](https://aws.amazon.com/blogs/mobile/getting-more-visibility-into-graphql-performance-with-aws-appsync-logs/)

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

## Count of Requests Per Minute

```
stats count(*) as CNT by bin(60s)
| filter logType = "RequestSummary"
| sort CNT desc
```

## Top 10 Resolvers By Duration

```
fields resolverArn, duration
| filter logType = "Tracing"
| sort duration desc
| limit 10
```
