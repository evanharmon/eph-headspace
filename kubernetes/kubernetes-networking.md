# KUBERNETES NETWORKING

## Summary

General notes on networking in K8S

## Resources

[Networking Guide](https://kubernetes.io/docs/concepts/cluster-administration/networking/)
[Service Networking](https://kubernetes.io/docs/concepts/services-networking/service/)

## Pods

Every POD gets it's own IP address. No need to create links across containers
like in Docker. No need to map container / host ports.

## Pods Localhost

IP-per-Pod model. All containeirs within the same pod can communicate with each other over
localhost. Containers must coordinate port usage.
