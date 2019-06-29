# elk-kubernetes
Setup ELK in Kubernetes

## Notes

### Deploying the Kubernetes Dashboard UI
See [documentation](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/). To protect your cluster data, Dashboard deploys with a minimal RBAC configuration by default. Currently, Dashboard only supports logging in with a Bearer Token. To create a token for this demo, you can follow our guide on creating a [sample user](https://github.com/kubernetes/dashboard/wiki/Creating-sample-user).
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/master/aio/deploy/recommended/kubernetes-dashboard.yaml
```
```
kubectl proxy
```
Kubectl will make Dashboard available at http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/.

Find admin-user token that was created.
```
kubectl -n kube-system describe secret 
```
### Create deployments
```
kubectl apply -f controllers\logstash-deployment.yaml
```
### Exporting Anaconda Environment
For more details, refer to the [comprehensive guide](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?highlight=environment).
```
conda env export > environment.yml
```
