# Commands
## Chapter 3
### Cluster status
- `kubectl version`
- `kubectl get componentstatuses`

### List nodes
- `kubectl get nodes`
- `kubectl describe nodes node-1`

### Cluster Components
#### Proxy
- `kubectl get daemonSets --namespace=kube-system kube-proxy`

#### DNS
- `kubectl get deployments --namespace=kube-system kube-dns`
- `kubectl get services --namespace=kube-system kube-dns`

#### UI
- `kubectl get deployments --namespace=kube-system kube-dashboard`
- `kubectl get services --namespace=kube-system kube-dashboard`
- `kubectl proxy`