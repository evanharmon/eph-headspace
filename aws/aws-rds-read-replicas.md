# AWS RDS READ REPLICAS

## Requirements
Automatic backups must be turned on
Can only be multi-az if the source database is set for Multi-AZ

## Creation
Instance size can be different from original
AZ can be different than current AZ

## Limitations
- up 5 Read Replicas of any databases
- you can have replicas of replicas but they can incur extra latency
- CANNOT take snapshots or automated backups of read replicas

## Data Transfer On Creation
Free!

## Use
Uses async replication
Good for read-heavy workloads
Used for Scaling
Each Replica has its own DNS end pont
Can be promoted to be their own databases, breaking the replication

## Regions
Read replica in a second region for MySQL and MariaDB

## Supports
MySQL Server
PostgreSQL
MariaDB
