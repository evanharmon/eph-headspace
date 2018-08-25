# AWS DYNAMODB BATCH ITEMS

## Cost
non-existent items consume 1 or .5 RCU
deletes cost 1 WCU - even if item doesn't exist

## BatchGetItem
- single request can retrieve items from multiple tables

### Limitations
- retrieve up to 1mb of data
- limited to 100 items

## Operations
limited to 16MB return
items are atomic, the batch is not
done in parallel
results are UNORDERED
1 operation type per ITEM - more and entire operation fails
if KEY attributes don't match - entire operation fails

## BatchWriteItem
done in parallel but order cannot be guaranteed

### Limitations
- up to 25 items
- 400KB item limit
- 16MB total request limit

## Operations
- each item is written separately - still have the per-item waste
- unprocessed items are returned
- if all items fail, then the operation fails
- can be used for PUT and DELETE
