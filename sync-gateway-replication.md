# SYNC GATEWAY REPLICATION

## Docs
https://developer.couchbase.com/documentation/mobile/1.4/guides/sync-gateway/running-replications/index.html

## Replication Types
### Push / Pull
- Inside a sync gateway
- Between sync gateways
- Can do continuous or one time example at midnight

### Replication by Territory
example - only replicate this specific channel to data centers in Germany

## Testing Changing Sync Function
insert picture from phone
canary / qa check new sync function on a new bucket - not connected to LB / public
DB1 / 2 bucket 2 is replica of bucket 1
you can keep it all as DB1 if you want, bc new SG can have diff ip address

## Setup a replication
POST to `/_replicate`
```
{
  "source": "db",
  "target": "db2"
}
```
