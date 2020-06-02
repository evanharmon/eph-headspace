# AWS RDS

## List Of Relational Databases Available On AWS
MariaDB
Aurora
MS Sql Server
Oracle
MySQL
PostGRES

## Scaling
- cannot scale instance size as quickly / easily as DynamoDB
- very manual process
- you can really only scale up
- can scale out for reads but NOT writes

## Limitations
### Vendor Limits
MySQL/Oracle max db storage size of 6TB
Oracle: 1

### Instances
Up to 40
Up to 10 Oracle
up to 10 SQL Server. Can go up to 30 if bring your own license

### SQL Server Storage Size
Increasing Storage on RDS NOT supported on SQL Server

## DMS (Database Migration Service)
Uses Schema migration tool to migrate from one database tool to a different
database (ex. Oracle to Aurora). Works with functions, stored procedures,
functions, etc

## Data Warehousing on AWS
Tools like Cognos, Jaspersoft, SQL Server Reporting Services, Oracle Hyperion,
SAP NetWeaver. Used to pull in very large and complex data sets. Management
loves to do queries on the data for KPI's, targets, etc

## OLTP Online Transaction Processing
Limited # of records

## OLAP Online Analytics Processing
Redshift is much better for analyzing large amount of information, lots of
queries, large # of records

## Reserved Instances
Reservedb by region not by az

## Best Practices

### Upgrade To New Versions
make a snapshot, launch new from snapshot
