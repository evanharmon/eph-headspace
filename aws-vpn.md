# AWS VPN

## Use Case
- immediate need
- low to modest bandwidth requirements
- can tolerate variability in internet-based connectivity

## Internet Traffic
Route and Security groups can be set up to have vpn network traffic go back
directly to public subnet instead of out over the internet

## Communicate To AWS Environment From On Premise
Assign public IP address to VPC Gateway

## Setup
[How To](https://medium.com/@mda590/aws-routing-101-67879d23014d) scroll down
to `Routing via a VPN`
- On-Premise Customer Gateway
- Virtual Private Gateway
- VPC with Hardware VPN Access

Route Propogation must be turned on in every route table
