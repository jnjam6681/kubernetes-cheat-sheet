## Prepare for autoscaling
#### Install Metrics Server
```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install --name metrics-server bitnami/metrics-server
```
