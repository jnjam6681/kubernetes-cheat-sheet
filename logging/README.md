## Logging
#### Prepare for setting up
Edit volumeClaimTemplates in elasticsearch-statfulset.yaml to your volume.
#### Forward the local
```
kubectl port-forward kibana-pod 5601:5601 --namespace=kube-system
```
#### Reference
```
https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch
```
