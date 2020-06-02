# AWS ROUTE 53 ROUTING POLICIES

## Simple (DEFAULT)
no Intelligence built in
commonly used for a single resource

## Weighted
Good for A/B testing in small portion of user base

## Latency
Used by creating latency resource record set for the ELB in each region
Route53 will choose the lowest latency resource record set

## Failover
Used with active/passive setup
Ex. Primary site in us-west-1 and secondary site in us-east-1
Always sends to primary unless primary fails

## Geolocation
You choose where traffic goes based on geolocation of the user DNS query
