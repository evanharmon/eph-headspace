# AWS EC2 NAT GATEWAY

## Limitations
- cannot be associated with a security group
- do not support ClassicLink connections
- natgateway with a status of pending, deleting, or available counts against the
limit
- natgateway with status of 'failed' is deleted in about an hour automatically
- can be TCP, UDP, or ICMP protocol
- does not support port forwarding, bastion servers, or traffic metrics

## IAM
- by default, IAM users do not have permission to work with NAT gateways
- does not support resource-level permissions for ec2:*NatGateway* API operations

## Connection Limitations
- does not support IP fragmentation for TCP (Use a NAT instance instead)
- idle connections dropped after 5 minutes
- do not support IPSec protocol
- supports up to 65000 simulatenous connections to a unique destination

## Routing
STATEFUL
- cannot send traffic over VPC endpoints, VPN Connections, AWS Direct Connect,
or VPC Peering Connections
- cannot route traffic through gateway to VPC Peering Connection, VPN
Connection, or AWS Direct Connect
- adjust the subnets route table to route directly to these resources. Works bc
the resource routing will be more specific than the nat routing 0.0.0.0/0

## Communication Across AZ's
- communicate across AZ's but are based in a single AZ
- if that AZ goes down, internet access goes down to instances/resources using
that NAT from other AZs
- create a NAT per AZ for failover tolerance

## BURST
support burst rate up to 10GBs
If you need more, create a NAT per subnet and distribute the workload across
subnets

## EIPs
Cannot be disassociated from a NAT instance after it's created. You would have
to terminate the NAT instance to free that elastic ip

## Securing Traffic
Use ACLs to control traffic to/from subnets

## Ports
NATs use ports 1024 - 65535

## Network Interface
elastic network interface (ENI) is created upon a NAT creation. This ENI cannot
be modified

## Testing
- use traceroute and see if the private ip address of that nat instance comes up
- use a third-party website to make sure the traffic ip address is the NAT
public ip address
