# AWS EC2 VPC SECURITY GROUPS

## Summary

Notes on working with security groups in AWS

## Overview

- first layer of defense
- stateful, return traffic allowed automatically, regardless of any rules
- every instance must have a security group, if you don't specify one, the
  default vpc security group is assigned

## Limitations

- can only have one ACL attached
- do not affect traffic on 169.254.0.0/16

## DELETE THIS SECURITY GROUP IF YOU EVER SEE IT

2009-07-15-default

## Instance SG

attached to DeviceIndex 0 (eth0)

## Can span across multiple subnets

ex: you can attach the same SG to the private and public subnet instances

## Defaults

- outbound traffic defaults to all allowed
- inbound traffic defaults to none allowed

## Communication Between Security Groups

- default security group has rules to allow communication between instances
  assigned to this group
- manually created Security Groups DO NOT have this rule and it must be added
  explicitly in order for instances to communicate with another Security Group
