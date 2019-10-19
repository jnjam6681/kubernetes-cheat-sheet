## Prepare for autoscaling
#### Install Metrics Server
```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install --name metrics-server bitnami/metrics-server
```
#### Reference
```
https://www.digitalocean.com/community/tutorials/how-to-autoscale-your-workloads-on-digitalocean-kubernetes#step-4-%E2%80%94-creating-and-validating-the-horizontal-pod-autoscaler
```
