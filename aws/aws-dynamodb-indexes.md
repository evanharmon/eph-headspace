# AWS DYNAMODB INDEXES

## Summary

Notes on using global and local secondary indexes on Dynamodb

## Resources

- [Create, Monitor, and Optimize GSI](https://aws.amazon.com/premiumsupport/knowledge-center/create-gsi-dynamodb/)

### Limitations

up to 5 of each per table

### Primary Keys

- hash / partition key of one attribute

### Composite Keys

- hash key and sort key
- two items can then have same partition key
- sorting by partition key / sort key

### Local Secondary Indexes (LSI)

- can only be created at time of table creation
- allow an alternative sort key to be used
- max total size of elements is 10GB per partition key value
- SAME partition key, different sort key

### Global secondary indexes (GSI)

- can be added at table creation or later
- supports non-unique attributes
- different partition / sort key

#### Monitor Creation

Cloudwatch metrics, search for `OnlineIndexPercentageProgress` and graph it
