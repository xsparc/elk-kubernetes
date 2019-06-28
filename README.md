# elk-kubernetes
Setup ELK in Kubernetes

Uses HyperV driver. Refer to the [guidelines](https://github.com/kubernetes/minikube/blob/master/docs/drivers.md#hyperv-driver).

### Project Instances
```
minikube start
```

### Minikube config 
For PXI
```
minikube config set vm-driver hyperv && minikube config set hyperv-virtual-switch "Hyperv Virtual Switch" && minikube config set memory 4096 && minikube config set cpus 2
```
For Desktop
```
minikube config set vm-driver hyperv && minikube config set hyperv-virtual-switch "Hyperv Virtual Switch" && minikube config set memory 3000 && minikube config set cpus 2
```

### Turning off Minikube
```
$ minikube ssh
$ sudo poweroff
```
### Create deployments
```
kubectl apply -f controllers\logstash-deployment.yaml
```