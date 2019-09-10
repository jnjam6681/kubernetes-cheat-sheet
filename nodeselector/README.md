## nodeSelector
#### Add a label node
```
kubectl label nodes <node-name> <label-key>=<label-value>

kubectl label nodes slave-01 disktype=ssd
```
#### Get labels
```
kubectl get node
kubectl get node --show-labels
```
#### Remove label
```
kubectl label nodes slave-01 disktype=ssd-
```
