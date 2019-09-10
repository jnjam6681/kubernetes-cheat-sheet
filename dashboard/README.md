## Setting up the dashboard
#### Install Metrics Server
```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install --name metrics-server bitnami/metrics-server
```
#### Create Dashboard
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml
```
#### Create ServiceAccount
```
kubectl apply -f dashboard-service-account.yaml
```
#### Create ClusterRoleBinding
```
kubectl apply -f dashboard-cluster-role-binding.yaml
```
#### Get Bearer Token
```
kubectl -n kube-system describe secret $(kubectl -n kube-system get secret | grep admin-user | awk '{print $1}')
```
