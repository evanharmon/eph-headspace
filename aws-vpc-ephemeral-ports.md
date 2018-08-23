# AWS VPC EPHEMERAL PORTS

## Client's in VPC
If an instance in the VPC is the client initiating request, need an inbound ACL
to allow correct ephemeral ports. Probably want to first add DENY rules for
malicious ports, then a rule for ALLOW Range
