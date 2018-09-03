# KUBERNETES CONFIGURATION FILES
(https://raw.githubusercontent.com/mhausenblas/kbe/master/specs/pods/constraint-pod.yaml)

## Single Deployment Configuration
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
