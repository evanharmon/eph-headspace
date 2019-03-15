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
