# KUBERNETES PODS

(http://kubernetesbyexample.com/pods/)

## Run A Docker Image In A Pod

Equivalent to `docker run` and `docker-compose start`
creates a deployment

```console
$ kubectl run sise --image=mhausenblas/simpleservice:0.5.0 --port=9876
```

## Delete A Deployment

```console
$ kubectl delete deployment sise
```

## Create A Pod From A Configuration File

```console
$ kubectl create -f \
  https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/pods/constraint-pod.yaml
```

## Exec In To A Container

```console
kubectl exec worker-deployment-c5dcfb5bf-scjq5 -i -t -- bash
```

## Check Logs

```console
kubectl logs pod-name
```
