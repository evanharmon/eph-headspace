# KUBERNETES MINIKUBE

## Create And Start A K*8S Cluster On MacOS
$`minikube start --kubernetes-version v1.10.0 --vm-driver=hyperkit`

## Stop A Cluster
Preserves cluster and data
$`minikube stop`

## Delete A Cluster
Deletes cluster and data
$`minikube delete`

## List All Kubernetes Versions
$`minikube get-k8s-versions`

## Get IP Of Cluster
$`minikube ip`

## Use Docker Commands For Minikube
$`eval $(minikube docker-env)`

## View Dashboard
$`minikube dashboard`

## Persisting Data
Minikube configured to persist files stored in:
/data
/var/lib/localkube
/var/lib/docker

## Persistant Volume
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv0001
spec:
  accessModes:
    - ReadWriteOnce
  capacity:
    storage: 5Gi
  hostPath:
    path: /data/pv0001/
```
