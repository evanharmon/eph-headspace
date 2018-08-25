# AWS SYSOPS MULTI
Active to active configuration

## Replication
Async or sync. Depends on how low RPO needs to be

## Cost
Determined by how much production traffic goes to second site

## Preparation Phase
- setup duplicate production AWS environment
- Setup DNS weighting / traffic routing to both environments. Configure
automated failover

## Recovery Phase
- Change DNS weighting manually or automatically with Route53 to failover site
- Have application logic for failover to switch database servers queried
- Consider using auto scaling to right size fleet
