# AWS EC2 NAT INSTANCES
If NAT Becomes Bottleneck - Increase The Instance Size

## Source / Destination Check Must Be DISABLED
Normally AWS checks to make sure the instance is the source and destination of
traffic - but a NAT needs to forward traffic so this must be disabled

## Defaults
IPv4 forwarding enabled
ICMP disabled at /etc/sysctl.d/10-nat-settings.conf
Iptables IP masquerading script /usr/sbin/configure-pat.sh
support port forwarding, bastion servers, or traffic metrics
