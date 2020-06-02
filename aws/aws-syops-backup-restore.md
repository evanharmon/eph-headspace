# AWS SYSOPS BACKUP / RESTORE

## Replication Of Data Factors
Distance between sites
Available bandwidth
Data rate required by application
Replication technology

# Failing Back From A Disaster
Backup and Restore steps
- freeze data changes to DR site
- take backup
- restore the backup to primary site
- re-point users to primary site
- unfreeze changes

# Failing Back From A Disaster
Pilot Light, Warm Standby, and Multi-Site
- establish reverse mirroring / replication from DR site back to primary site,
once the primary site has caught up with the changes
- freeze data changes to DR site
- re-point users to primary site
- unfreeze changes

# S3
Use to transfer / copy data between regions
Snapshots of Ebs, rds, red shift

# Key Steps
- Select appropriate tool / method
- Ensure appropriate retention policy
- Ensure appropriate security measures including cryptography and access
policies
- Regularly test recovery of data and restoration of system
