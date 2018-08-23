# AWS RDS BACKUPS

## Limitations
max storage is 35 days for backups

## Restoring
new DB Instance Identifier is required
restore always will have a new endpoint

## Automated Backups
- between one and 35 days
- takes full daily snapshots and store transaction logs through the day
- allows point in time recovery down to the second, within the retention period
- stored in S3
- free storage space up to the size of your database
- Backups taken within defined window, during window, storage I/O may be
suspended while data is being backed up leading to elevated latency
- delete along with RDS instance deletion

## Database Snapshots
- user initiated
- stored even after you delete the original RDS instance

## Window
- default is 30 minutes
- changes occur immediately
