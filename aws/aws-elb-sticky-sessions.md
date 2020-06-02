# AWS ELB STICKY SESSIONS

## Application Controlled
- app creates the cookie
- LB uses special cookie to associate session with original server
- LB follows lifetime of application-generated cookie corresponding to policy
config
- LB inserts new stickiness cookie if application response includes new app
cookie

## How To Remove Application Controlled Cookie
explicitly remove/expire application cookie
LB session stops being sticky until new app cookie is issued

## Duration Based
LB creates cookie if none exist
LB chooses an application instance and adds cookie in response

## Duration Based Expiration
stickiness policy configuration defines expiration
cookie auto updated after its duration expires
