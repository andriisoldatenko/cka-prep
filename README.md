## CKA preparation repo


Create kind cluster:

```bash
kind create cluster --name=cka-prep
```


### Creating services:

```bash
kubectl run echoserver --image=k8s.gcr.io/echoserver:1.10 --restart=Never --port=8080
```


```bash
kubectl run echoserver --image=k8s.gcr.io/echoserver:1.10 --restart=Never --port=8080 -l app=echoserver
kubectl create service clusterip echoserver --tcp=5005:8080
```