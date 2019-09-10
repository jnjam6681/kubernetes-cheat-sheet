## Taint And Tolerations
#### Taint a node
```
kubectl taint nodes <node-name> type=specialnode:NoSchedule
```
#### Taint a node with NoExecute
```
kubectl taint nodes <node-name> type=specialnode:NoExecute
```
#### Remove taint
```
kubectl taint nodes <node-name> type=specialnode:NoSchedule-
```
