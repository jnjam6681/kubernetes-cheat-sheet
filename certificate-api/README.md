## Certificate API

#### Generate a CA private key
```
openssl genrsa -out john.key 2048
```

#### Create a self signed Certificate
```
openssl req -new -key john.key -subj "/CN=john" -out john.csr
```

#### Encode base64
```
cat john.csr | base64
cat john.csr | base64 | tr -d '\n'
```
Get result and put data under spec.request in YAML.

#### Create a Certificate Signing Request object to send to the Kubernetes API
```
kubectl apply -f certificate-signing-request-csr.yaml
kubectl get csr
```

#### Approve the CSR Request
```
kubectl certificate approve john
```

#### Reject the CSR Request
```
kubectl certificate deny john
```

#### Delete the CSR Object
```
kubectl delete csr john
```

#### Reference
```
- https://kubernetes.io/docs/tasks/tls/managing-tls-in-a-cluster/
- https://kubernetes.io/docs/tasks/administer-cluster/kubeadm/kubeadm-certs/
```
