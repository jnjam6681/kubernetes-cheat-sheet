## KubeConfig

#### Describe one or many contexts 
```
kubectl config  get-contexts
```

#### Displays the current-context
```
kubectl config view
kubectl config view --kubeconfig=[current_context]
```

#### Sets the current-context in a kubeconfig file
```
kubectl confin use-context [current_context]
kubectl config --kubeconfig=/root/my-kube-config use-context [current_context]
```

#### References
```
- https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/
- https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-certs/
```
