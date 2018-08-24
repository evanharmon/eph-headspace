# AWS EC2 FIREWALL
Changes go in to effect IMMEDIATELY

## Mandatory Inbound Firewall
- default deny-all-mode
- ports must be explicitly opened

## Restriction Types
- Protocol
- Service Port
- IP Address or CIDR block


## Rules
Everything is disallowed unless explicitly made allowed
- all inbound traffic is blocked by Default
- all Outbound traffic is allowed by Default
- can only add 'allow' rules. Cannot add a 'disallow' rule

## Security Groups are STATEFUL
Any allow rule added to inbound is automatically added to outbound

### Example 1
Web servers with port 80 (HTTP) and/or port 443 (HTTPS) open
App servers with port 8000 only accessible to server group
Database servers with port 3306 only accessible to app server group
All groups with port 22 (SSH) open to customer's corporate network
