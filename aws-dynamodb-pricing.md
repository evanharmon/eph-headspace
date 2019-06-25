# AWS DYNAMODB PRICING

Cheap for reads - expensive for writes

## Summary

Notes on dynamodb pricing

## On Demand
No scaling setup necessary
Remember not to specify read or write capacity units on global indexes if table
is set to on demand

## Provisioned Throughput Capacity

- write throughput \$0.0065 per hour for every 10 units
- read throughput \$0.0065 per hour for every 50 units
- write capacity units can handle 1 write per second

## Storage

\$0.25Gb per month

## Example 1:

Assuming storage 3gb, 1 mm writes per day, 1mm reads per day
11.6 writes per second
11.6 reads per second
Write capacity units = (0.0065/10) x 12 x 24 = $0.1972
Read capacity units = (0.0065/50) x 12 x 24 = $0.0374
