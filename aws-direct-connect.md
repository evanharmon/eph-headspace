# AWS DIRECT CONNECT
- does not involve the internet
- uses dedicated, private network connections between intranet and Amazon VPC

## Use Case
- reduce costs when using large volumes of traffic
- increase reliability
- increase bandwidth with AWS
- do not want internal traffic traversing the internet

## Setup Steps
- get a dedicated line from a Tel Co to an AWS Direct Connect facility
- dedicated line is terminated in private rack/cage at AWS Direct Connect
Facility
- AWS Dark fibre used from private rack/cage straight to AWS Data Center

## Speed Options
- 10Gbps
- 1Gbps
- Sub 1Gbps thru AWS Direct Connect Partners
- Uses Ethernet VLAN trunking (802.1Q)

## AWS to On-Premise Connections
- enable Route Propogation on Virtual Private Gateway (VPG)
- edit VPC subnet route table and add route back to on-premise data center
