# APPSYNC VTL

## Summary

Notes on using VTL with appsync

## Resources

[Resolver VTL Programming](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-mapping-template-reference-programming-guide.html)
[Context](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-context-reference.html)
[VTL Utility Functions](https://docs.aws.amazon.com/appsync/latest/devguide/resolver-util-reference.html)

## Request Mapping

#### Check For Input Field And Throw Error

```
#if( $util.isNullOrEmpty($context.args.input.id) )
  $util.error("input object missing required field: id")
#end
```

#### Optional Auto-Generated ID

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

#### Query Partition Key And Sort / Range Key

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

#### DynamoDb UpdateItem With Condition

attribute_exists

```vtl
{
  "version": "2018-05-29",
  "operation": "UpdateItem",
  "key": {
    "id": { "S": "$id" },
    "sortKey": { "S": "$sortKey" }
  },
  "update": $util.toJson($update),
  "condition": {
    "expression": "attribute_exists(id) and attribute_exists(sortKey)"
  }
}
```

#### Prevent Overwriting Create Timestamp Type Field

[SO](https://stackoverflow.com/questions/53666369/how-to-upsert-item-in-dynamodb-and-maintain-createdat-and-updatedat-fields)

```vtl
// use if_not_exists()
UpdateExpression: `SET #QQ_ID = :answer, #updatedAt = :updatedAt, #createdAt = if_not_exists(#createdAt, :createdAt)`,
ExpressionAttributeNames: {
    '#QQ_ID'   : `QQ_${question_id}`,
    '#updatedAt': 'UpdatedAt',
    '#createdAt': 'CreatedAt',
},
ExpressionAttributeValues: {
    ':answer': answer,
    ':updatedAt' : now.toISOString(),
    ':createdAt' : now.toISOString(),
}
```

via if statement using AWS boilerplate vtl for upserts

```vtl
#if( $entry.key == "#createdAt" )
  #set( $expression = "$expression $entry.key = if_not_exists($entry.key, $entry.value)" )
#else
  #set( $expression = "$expression $entry.key = $entry.value" )
#end
```

## Response Mapping

use `$ctx`. `$context` references won't work!

#### Correctly Throw Error In Response Template Mapping

```vtl
#if ( $ctx.error )
    $util.error($ctx.error.message, $ctx.error.type)
#end
$util.toJson($ctx.result)
```

#### Stash In Response Mapping

```vtl

#if ( $ctx.error )
    $util.error($ctx.error.message, $ctx.error.type)
#end
$util.qr($context.stash.put("latestVersionNumber", $ctx.result.versionNumber))
$util.toJson($ctx.result)
```

## Check TypeOf

```vtl
$util.typeOf("$context.identity.groups")
```
