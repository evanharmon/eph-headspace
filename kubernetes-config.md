# KUBERNETES CONFIG

## SUMMARY

Notes on configuring kubernetes

## Resources

[Docs](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)

## View Config

```console
kubectl config view
```

## Change Current Context

```console
kubectl config use-context my-other-context-name
```

## Configure docker-for-mac

allows kubectl to be used inside a non-k8s docker container for local
development.

Example use case: developing inside a docker container for linux with Neovim on
a mac which has docker community edition / k8s support turned on.

~/.kube/config example with additional cluster and context

```
apiVersion: v1
clusters:
- cluster:
    insecure-skip-tls-verify: true
    server: https://127.0.0.1:6443
  name: docker-desktop
- cluster:
    insecure-skip-tls-verify: true
    server: https://docker.for.mac.localhost:6443
  name: docker-for-mac
contexts:
- context:
    cluster: docker-desktop
    user: docker-desktop
  name: docker-desktop
- context:
    cluster: docker-desktop
    user: docker-desktop
  name: docker-for-desktop
- context:
    cluster: docker-for-mac
    user: docker-desktop
  name: docker-for-mac
current-context: docker-for-mac
kind: Config
preferences: {}
users:
- name: docker-desktop
  user:
    client-certificate-data: REDACTED
    client-key-data: REDACTED
```
