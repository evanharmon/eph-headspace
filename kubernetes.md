# KUBERNETES (K8S)

## Summary

General notes on working with Kubernetes

## Requirements / Installation

The easiest method for using Kubernetes locally is through Docker Community
Edition.

[Create An Account And Install Docker Community Edition](https://store.docker.com/editions/community/docker-ce-desktop-mac)

[Enable Kubernetes on Docker](https://docs.docker.com/docker-for-mac/#kubernetes)
or use [Minikube](https://github.com/kubernetes/minikube)

## Resources

[Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

## Documentation

[Kubernetes.io Docs](https://kubernetes.io/docs/home/?path=users&persona=app-developer&level=foundational)

[Pods](https://kubernetes.io/docs/concepts/workloads/pods/pod-overview/)

[Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

[Services](https://kubernetes.io/docs/concepts/services-networking/service)
[Labels / Selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/labels/)

## Tutorials / Learning

[Interactive Tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/expose/expose-interactive/)
[Udemy Learn DevOps: The Complete Kubernetes Course](https://www.udemy.com/learn-devops-the-complete-kubernetes-course/learn/v4/overview)

[Kubernetes By Example](http://kubernetesbyexample.com/)

## Installation

[Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-linux)

## Dashboard

Deploying and access the dashboard requires the below steps to be completed:

Deploy dashboard, get pod name, and expose locally

```console
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0-beta1/aio/deploy/recommended.yaml
kubectl get pods --namespace=kubernetes-dashboard
kubectl port-forward kubernetes-dashboard-7798c48646-ctrtl 8443:8443 --namespace=kubernetes-dashboard
```

Get token for dashboard and login

```console
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | awk '/^deployment-controller-token-/{print $1}') | awk '$1=="token:"{print $2}' | pbcopy
open https://localhost:8443
```

default dashboard address: `http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/`
