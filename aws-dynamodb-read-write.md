# AWS DYNAMODB READ WRITE

## Summary

Notes on read and write capacity units in DynamodB

## Calculating Capacity Units

writes are easy 1KB

- size of read rounded to nearest 4KB / 4
- result times no of items.
- divide by 2 if eventually consisent

## Read / Write Capacity

- set per Table
- can be changed at any time. It's an ASYNC operation
- allocated on a per second basis

## Reads

Can range from 0.5 to 100 RCUs based on max 400KB item size

### Read Capacity Unit

One read capacity unit represents one strongly consistent read per second per
item up to 4KB

- up to 4KB data, always rounded up
- Get request always uses 1 RCU or more
  Ex: 6KB Read = 6KB / 4 = 1.5 = 2RCU

### Read Provisioned Throughput

- rounded up to increments of 4KB
- Eventually consistent reads (default) 2 read per second

## Writes

Can range from 1 to 400 WCUs based on max 400KB item size

### Write Capacity Unit

One write capacity unit represents one write per second per item up to 1KB

- up to 1KB data
- Get request always uses 1 WCU or more
  Ex: 1.5KB Write = 1.5 / 1 = 1.5 = 2WCU

### Write Provisioned Throughput

- ALL are 1KB
- ALL are 1 write per second

## Capacity Limits

- cannot decrease capacity units more than 4 times per day
- can increase as much as you want

## Eventual Consistent Reads

consume HALF the RCU resources, halved at the END of raw RCU units calculation
Ex: 8KB Read = 8KB / 4 = 2 _ 0.5 = 1RCU
Ex: 10KB Read = 10 / 4 = 2.5 = 3RCU _ 0.5 = 1.5RCU = 2RCU
This is the default

## Excessive Read / Write Capacity

Anything more than 3,000 RCU or 1,000 WCU needs special consideration

## Attribute Names

short attribute names can make a big difference on a large table, and large
amount of read/writes
