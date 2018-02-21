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

## Chapter 4 (Common kubectl commands)
### Namespaces
- `--namespace=<NAMESPACE>`

### Contexts
- `kubectl config set-context my-context --namespace=mystuff`
- `kubectl config use-context my-context`

### Viewing Kubernetes API objects
- `kubectl get <resource-name> <object-name>`
- More information: `-o wide`
- JSON: `-o json`
- YAML: `-o yaml`
- No headers: `--no-headers`
- Detailed information about particular object: `kubectl describe <resource-name> <object-name>`

### Creating, updating & destroying objects
- Create: `kubectl apply -f obj.yaml`
- Update: `kubectl apply -f obj.yaml`
- Edit interactively: `kubectl edit <resource-name> <object-name>`
- Delete: `kubectl delete -f obj.yaml` or `kubectl delete <resource-name> <object-name>`

### Labeling & annotating objects
- Set label: `kubectl label pods bar color=red`
- Overwrite existing label: `--overwrite`
- Remove label: `kubectl label pods bar -color`

### Debugging
- Logs: `kubectl logs <pod-name>`
- Streaming logs: `-f`
- Interactive shell in a pod: `kubectl exec -it <pod-name> -- bash`
- Copy files: `kubectl cp <pod-name>:/path/to/remote/file /path/to/local/file`

### Help
- `kubectl help`
- `kubectl help <command-name>`


## Chapter 5 (Pods)
### Creation
- Imperative: `kubectl run kuard --image=gcr.io/kuar-demo/kuard-amd64:1`
- From manifest: `kubectl apply -f kuard-pod.yaml`

### Deletion
- `kubectl delete deployments/kuard`
- `kubectl delete -f kuard-pod.yaml`

### Listing
`kubectl get pods`

## Description
`kubectl describe pods kuard`

## Port forward
`kubectl port-forward kuard 8080:8080`

## Get logs
`kubectl logs <pod-name> [-f]`

## Execute in container
- `kubectl exec <pod-name> date`
- Interactive: `kubectl exec -it <pod-name> ash`

## Copy files to/from container
- From: `kubectl cp <pod-name>:/captures/capture3.txt ./capture3.txt`
- To: `kubectl cp $HOME/config.txt <pod-name>:/config.txt`

## Chapter 6 (Labels & annotations)
### Labels
