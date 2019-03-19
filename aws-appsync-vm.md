# APPSYNC VTL

## Summary

Notes on using VTL with appsync

## Resources

[Resolver VTL Programming](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-programming-guide.html)
[Context](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-context-reference.html)
[VTL Utility Functions](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-util-reference.html)

## Check For Input Field And Throw Error

```
#if( $util.isNullOrEmpty($context.args.input.id) )
  $util.error("input object missing required field: id")
#end
```

## Optional Auto-Generated ID

```vtl
{
  "version": "2017-02-28",
  "operation": "PutItem",
  "key": {
      "id":     $util.dynamodb.toDynamoDBJson($util.defaultIfNullOrBlank($ctx.args.input.id, $util.autoId()))
  },
  "attributeValues": $util.dynamodb.toMapValuesJson($context.args.input),
  "condition": {
      "expression": "attribute_not_exists(#id)",
      "expressionNames": {
          "#id": "id"
    }
  }
}
```

## Query Partiion Key And Sort/Range Key

[SO](https://stackoverflow.com/questions/52580083/aws-app-sync-dynamodb-resolver-usage-with-begin-with-expression-in-sort-key-not)

```vtl
https://stackoverflow.com/questions/52580083/aws-app-sync-dynamodb-resolver-usage-with-begin-with-expression-in-sort-key-not{
  "version": "2017-02-28",
  "operation": "Query",
  "query": {
    "expression": "id = :id and begins_with(sortKey, :sortKey)",
    "expressionValues": {
      ":id":      $util.dynamodb.toDynamoDBJson($ctx.args.id),
      ":sortKey": $util.dynamodb.toDynamoDBJson("ssk")
    },
  }
}
```
