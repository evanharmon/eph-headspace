# AWS DYNAMODB

## Summary

Notes on using DynamoDB

## Resources

[Hash / Range Keys](https://stackoverflow.com/questions/29178855/what-is-the-use-of-a-hash-range-in-a-dynamodb-table)

## Features

- stored on SSD
- spread across 3 geographically distinct data centres
- writes are processed in the order in which they are received

## Eventual Consistent Reads Model

Consistency across all copies of data is usually reached within a second.
Repeating a read after a short time should return the updated data.
(Best Read Performance)

## Strongly Consistent Reads Model

Consistent read returns a result that reflects all writes that received a
successful response prior to the read

## DynamoDB Structure

```
- Table
  - Items (Think Row)
    - Attributes (one or more - can be different)
      - Hash / Partition Key (Primary Index)
      - Range / Sort Key (Think Composite Key like timeseries data is stored)
```

## Scalar Attribute Family Type

Types: String, Number, Binary, Boolean

## Set Attribute Family Type

Sets of Scalar types
Types: String Set, Number Set, Binary Set (set of scalar types)
All of the same data type
unordered set of data - order is not preserved

## Document Attribute Family Type

Types: List, Map
List (ordered Array), supports diff types just like an array like strings, bool, number, etc
Map (think JSON)

## Limitations

400KB item size limit

## Atomic Counters

are NOT idempotent, use when data can accept some margin of error

## Exports

CSV - table or individual items

## Scaling - Push Button

still available while scaling up

## Access Control Lists

identity provider control over get / put / delete / update

# Streams

think triggers for lambda
used to capture modifications to tables

- stores for max 24 hours
