## KubeConfig

#### Generate a CA private key
```
openssl genrsa -out john.key 2048
```

#### Create a self signed Certificate
```
openssl req -new -key john.key -subj "/CN=john" -out john.csr
```
Or
```
openssl req -new -key john.pem -out john-csr.pem -subj "/CN=john"
openssl x509 -req -in john-csr.pem -CA ca.crt -CAkey ca.key -CAcreateserial -out john.crt -day 10000
```

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
kubectl config use-context [current_context]
kubectl config --kubeconfig=/root/my-kube-config use-context [current_context]
```
Or
```
kubectl config set-credentails john --client-certificate=john.crt --client-key=john.pem
kubectl config set-context john --cluster=kubernetes.john --user john
```
---
#### Get CA
```
kubectl config view -o jsonpath='{.clusters[0].cluster.certificate-authority-data}' --raw | base64 --decode - > k8s-ca.crt
```

#### Set CA and create kubeconfig
```
kubectl config set-cluster $(kubectl config view -o jsonpath='{.clusters[0].name}') --server=$(kubectl config view -o jsonpath='{.clusters[0].cluster.server}') --certificate-authority=k8s-ca.crt --kubeconfig=bob-k8s-config --embed-certs
```

#### Set user key to kubeconfig
```
$ kubectl config set-credentials bob --client-certificate=bob-k8s-access.crt --client-key=bob-k8s.key --embed-certs --kubeconfig=bob-k8s-config
```

#### Set Context kubeconfig
```
kubectl config set-context bob --cluster=$(kubectl config view -o jsonpath='{.clusters[0].name}') --user=bob --kubeconfig=bob-k8s-config
```

#### References
- [`https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/`](https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/)
- [`https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-certs/`](https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-certs/)
