# AWS DYNAMODB PERFORMANCE

## Read / Write Capacity
- set per Table
- can be changed at any time. It's an ASYNC operation
- allocated on a per second basis

## Capacity Limits
- cannot decrease capacity units more than 4 times per day
- can increase as much as you want

## Read Capacity Unit
- up to 4KB data, always rounded up
- Get request always uses 1 RCU or more
Ex: 6KB Read = 6KB / 4 = 1.5 = 2RCU

## Write Capacity Unit
- up to 1KB data
- Get request always uses 1 WCU or more
Ex: 1.5KB Write = 1.5 / 1 = 1.5 = 2WCU

## Excessive Read / Write Capacity
Anything more than 3,000 RCU or 1,000 WCU needs special consideration

## Eventual Consistent Reads
consume HALF the RCU resources, halved at the END of raw RCU units calculation
Ex: 8KB Read = 8KB / 4 = 2 * 0.5 = 1RCU
Ex: 10KB Read = 10 / 4 = 2.5 = 3RCU * 0.5 = 1.5RCU = 2RCU
This is the default

## Attribute Names
short attribute names can make a big difference on a large table, and large
amount of read/writes
