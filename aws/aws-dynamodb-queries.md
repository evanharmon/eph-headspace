# AWS DYNAMODB QUERIES

## Query
- finds item using only primary key. Partition key attribute name and distinct
value
- optinally use sort key with comparison operator
- sorted by Sort key, ascending order. Reverse order with
ScanIndexForward = false
- eventually consistent but can be changed to strongly consistent

## Scan
- returns all data attributes for primary key, use ProjectionExpression to stop
returning all attributes
- you can max out throughput in one scan!!

