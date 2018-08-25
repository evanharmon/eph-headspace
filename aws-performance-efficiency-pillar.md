# AWS PERFORMANCE EFFICIENCY PILLAR

## Covers
computing resource efficiency to meet requirements
maintaining efficiency as demand changes / technology evolves

## Design Principles
Democratize advanced technologies (consume svcs where possible)
Go Global in minutes
Use server-less architectures

## Definitions
Compute - Autoscaling
Storage - EBS, S3, Glacier
Database - RDS, DynamoDB, Redshift
Space-time tradeoff - ElastiCache, Cloud Front, Direct Connection, RDS Read Replicas

## Best Practices

### Compute Questions
How do you select the appropriate instance type for your system?
How do you ensure that you continue to have the most appropriate instance type
as new instance types and features are introduced?
How do you monitor your instances after launch to ensure they are performing as
expected?
How do you ensure that the quantity of your instances matches demand?

### Storage
depends on these factors:
Access Method - Block, File or Object
Patterns of Access - Random / Sequential
Throughput Required
Frequency of Access - Online, Offline or Archival
Frequency of Update - Worm, Dynamic
Availability Constraints
Durability Constraints

### Storage Questions
How do you select the appropriate storage solution for your system?
How do you ensure that you continue to have the most appropriate storage
solution as new storage solutions and features are launched?
How do you monitor your storage solution to ensure it is performing as expected?
How do you ensure that the capacity and throughput of your storage solutions
matches demand?

### Database Questions
How do you select the appropriate database solution for your system?
How do you ensure that you continue to have the most appropriate database
solution and features as new database solutions and features are launched?
How do you monitor your databases to ensure performance is as expected?

### Space-Time Trade-Off
On RDS use read replicas or create multiple copies to reduce latency
Use Direct Connect to provide predictable latency between your HQ and AWS
Use the global infrastructure to have multiple copies of your environment, in
regions closest to your customer base
Use caching services such as ElastiCache or CloudFront to reduce latency

### Space-time trade-off Questions
How do you select the appropriate proximity and caching solutions for your
system?
How do you ensure that you continue to have the most appropriate proximity and
caching solutions as new solutions are launched?
How do you monitor your proximity and caching solutions to ensure performance is
as expected?
How do you ensure that the proximity and caching solutions match demand?
