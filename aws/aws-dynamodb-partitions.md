# AWS DYNAMODB PARTITIONS

## General
- underlying storage and processing nodes of DynamoDB
- initially one table equal one partition
- cannot directly see # of partitions
- cannot directly control # of partitions (can affect the # thru configs though)

## Limitations
- partition can store 10GB of data
- partition can deliver 3000 RCU or 1000 WCU

## Performance
Based on a relationship between performance required, data stored, and number
of partitions

## Partitions
When Do Partitions Increase?
- data over 10GB
- RCU over 3000
- WCU over 1000

partition is then created, and data is spread between them over time
