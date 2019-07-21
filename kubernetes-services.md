# KUBERNETES SERVICES

## Summary

Notes on using services in Kubernetes. Services provide communication between
pods. Deployments can create and destroy Pods dynamically, so services provide
an abstraction known as `selectors`.

## Resources

[Connecting Pods](https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/)
[Connecting Client Side / Server Side](https://kubernetes.io/docs/tasks/access-application-cluster/connecting-frontend-backend/)
[Multi Port Support](https://kubernetes.io/docs/concepts/services-networking/service/#multi-port-services)
[Tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/expose/expose-intro/)

## Check For DNS Addon Service

Generic `kubectl` command, no need to change namespace, etc on docker mac

```console
kubectl get services kube-dns --namespace=kube-system
```

## Curl CoreDNS DNS Server

```console
kubectl run curl --image=radial/busyboxplus:curl -i --tty
```

## Get Endpoints For Service

```console
kubectl get ep my-nginx
```
