## Logging
#### Prepare for setting up
Edit volumeClaimTemplates in elasticsearch-statfulset.yaml to your volume.
#### Forward the local
```
kubectl port-forward kibana-pod 5601:5601 --namespace=kube-system
```
#### References
- [`https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch`](https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch)
- [`https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes`](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-elasticsearch-fluentd-and-kibana-efk-logging-stack-on-kubernetes)
