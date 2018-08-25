# AWS DYNAMODB GOTCHAS

## Global Secondary Index (GSI)
You can only query on GSI, you cannot delete or update on GSI. Use primary index
instead

## Local Secondary Index (LSI)
Can only be created at table creation

## Get vs. Query
- Get can only be used on primary key, always returns one record or none
- Query can be on primary, GSI, or LSI and can return more than one record
If you have a range key it is manditory “exactly equal" on get but optional and
has additional comparison options on query

## Attribute Definitions
Do not put attribute definitions in create-table if not part of a hash / range
index

## Attribute Data Type
Remember it's schema less. You can have integers and strings mixed in the same
column as values. It matters which data type you search for
