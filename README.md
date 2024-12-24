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


Exam tips:

https://kubernetes.io/docs/reference/kubectl/conventions/

### Create an NGINX Pod

`kubectl run nginx --image=nginx`

### Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)

`kubectl run nginx --image=nginx --dry-run=client -o yaml`

### Create a deployment

`kubectl create deployment --image=nginx nginx`

### Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)

`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml`

### Generate Deployment YAML file (-o yaml). Don’t create it(–dry-run) and save it to a file.

`kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml`

### Make necessary changes to the file (for example, adding more replicas) and then create the deployment.

`kubectl create -f nginx-deployment.yaml`

OR

>Note: In k8s version 1.19+, we can specify the --replicas option to create a deployment with 4 replicas.

`kubectl create deployment --image=nginx nginx --replicas=4 --dry-run=client -o yaml > nginx-deployment.yaml`
