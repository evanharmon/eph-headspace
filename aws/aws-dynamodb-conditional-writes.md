# AWS DYNAMODB CONDITIONAL WRITES
Use conditional writes when data is crucial - no margin of error

## Write Capacity Units (WCU)
- item doesn't exist, 1 WCU consumed
- item update fails, WCU are consumed based on size of item

## Idempotent
can send same request multiple times, will only affect item the first time
