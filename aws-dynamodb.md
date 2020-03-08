# AWS DYNAMODB

## Summary

Notes on using DynamoDB

## Resources

- [Hash / Range Keys](https://stackoverflow.com/questions/29178855/what-is-the-use-of-a-hash-range-in-a-dynamodb-table)
- [Medium TimeHop Dynamodb Strategies](https://www.timehop.com/news/2018/5/25/one-year-of-dynamodb-at-timehop)
- [NAB Tech Design Patterns](https://medium.com/@nabtechblog/advanced-design-patterns-for-amazon-dynamodb-354f97c96c2)
- [Restore Point In Time From Backup](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/pointintimerecovery_beforeyoubegin.html)
- [AWS Blog Workbench Preview](https://aws.amazon.com/blogs/aws/nosql-workbench-for-amazon-dynamodb-available-in-preview/)
- [Workbench Download](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/workbench.settingup.html)
- [AWS Blog Priority Queueing](https://aws.amazon.com/blogs/database/implementing-priority-queueing-with-amazon-dynamodb/)
- [Row Level Access Via Cognito Sub ID](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_examples_dynamodb_rows.html)

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

## IAM

### Limit Action Based On Cognito ID

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "dynamodb:DeleteItem",
        "dynamodb:GetItem",
        "dynamodb:PutItem",
        "dynamodb:Query",
        "dynamodb:UpdateItem"
      ],
      "Resource": ["arn:aws:dynamodb:*:*:table/MyTable"],
      "Condition": {
        "ForAllValues:StringEquals": {
          "dynamodb:LeadingKeys": ["${cognito-identity.amazonaws.com:sub}"]
        }
      }
    }
  ]
}
```
