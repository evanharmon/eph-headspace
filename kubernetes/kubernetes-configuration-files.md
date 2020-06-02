# KUBERNETES CONFIGURATION FILES

## Summary

Notes on yaml configuration files for k8s

## Resources

[Env Vars](https://kubernetes.io/docs/tasks/inject-data-application/define-environment-variable-container/)

## Single Deployment Configuration

[Example](https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/pods/constraint-pod.yaml)

```YML
apiVersion: v1
kind: Pod
metadata:
  name: constraintpod
spec:
  containers:
  - name: sise
    image: mhausenblas/simpleservice:0.5.0
    ports:
    - containerPort: 9876
    resources:
      limits:
        memory: "64Mi"
        cpu: "500m"
```

## Access Denied Pulling Image

If using local docker images that are pre-built, use the `imagePullPolicy: Never` setting

```console
spec:
  containers:
    - name: uses-local-image
      image: local-image-name
      imagePullPolicy: Always
```

## Share Local Machine Folder As Volume

```console
...
spec:
  containers:
    - name: worker
      volumeMounts:
        - name: awscredentials
          mountPath: /root/.aws
          readOnly: true
  volumes:
    - name: awscredentials
      hostPath:
        path: /Users/myusername/.aws
```
