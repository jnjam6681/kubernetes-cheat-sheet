# Kubernetes Cheat Sheet
## Viewing, Finding Resources
#### Nodes
* `kubectl get no`
* `kubectl get no -o wide`
* `kubectl describe no`
* `kubectl get no -o yaml`
* `kubectl get node --selector=[laber_name]`
* `kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=="ExternalIP")].address}'`
* `kubectl top node [node_name]`

#### Pods
* `kubectl get po`
* `kubectl get po -o wide`
* `kubectl describe po`
* `kubectl get po --show-lables`
* `kubectl get po -l app=nginx`
* `kubectl get po -o yaml`
* `kubectl get pod [pod_name] -o yaml --export`
* `kubectl get pod [pod_name] -o yaml --export > nameoffile.yaml`
* `kubectl get pods --field-selector status.phase=Running`

#### Logs
* `kubectl logs [pod_name]`
* `kubectl logs --since=1h [pod_name]`
* `kubectl logs --tail=20 [pod_name]`
* `kubectl logs -f [container_name] -c [pod_name]`
* `kubectl logs [pod_name] > pod.log`

#### Deployments
* `kubectl get deploy`
* `kubectl describe deploy`
* `kubectl get deploy -o wide`
* `kubectl get deploy -o yaml`

#### Service
* `kubectl get svc`
* `kubectl describe svc`
* `kubectl get svc -o wide`
* `kubectl get svv -o yaml`
* `kubectl get svc --show-labels`

#### Ingress
* `kubectl get ing`
* `kubectl get ing --all-namespaces`

#### PersistentVolume
* `kubectl get pv`
* `kubectl describe pv`

#### PersistentVolumeClaim
* `kubectl get pvc`
* `kubectl describe pvc`

#### Namespaces
* `kubectl get ns`
* `kubectl get ns -o yaml`
* `kubectl get describe ns`

#### DaemonSets
* `kubectl get ds`
* `kubectl get ds --all-namespaces`
* `kubectl describe ds [daemonset_name] -n [namespace_name]`
* `kubectl kubectl get ds [ds_name] -n [ns_name] -o yaml`

#### Events
* `kubect get events`
* `kubectl get events -n kube-system`
* `kubectl get events -w`

#### Service Accounts
* `kubectl get sa`
* `kubectl get sa -o yaml`
* `kubectl get serviceaccounts default -o yaml > ./sa.yaml`
* `kubectl replace serviceaccount default -f ./sa.yaml`

#### RepicaSet
* `kubectl get rs`
* `kubectl decribe rs`
* `kubectl get rs -o wide`
* `kubectl get rs -o yaml`

#### Roles
* `kubectl get roles --all-namespaces`
* `kubectl get roles --all-namespaces -o yaml`

#### Secrets
* `kubectl get secrets`
* `kubectl get secrets --all-namespaces`
* `kubectl get secrets -o yaml`

#### ConfigMaps
* `kubectl get cm`
* `kubectl get cm --all-namespace -o yaml`

#### StorageClass
* `kubectl get sc`
* `kubectl get sc -o yaml`

#### Multiple Resources
* `kubectl svc, po`
* `kubectl get deply, no`
* `kubectl get all`
* `kubectl get all --all-namespaces`

## Updating Resources
#### Taint
* `kubectl taint [node_name] [taint_name]`

#### Label
* `kubectl label [node_name] disktype==ssd`
* `kubectl label [pod_name] env=prod`

#### Cordon / Uncordon
* `kubectl cordon [node_name]`
* `kubectl uncordon [node_name]`

#### Drain
* `kubectl drain [node_name]`

#### Nodes / Pods
* `kubectl delete node [node_name]`
* `kubectl delete pod [pod_name]`
* `kubectl edit node [node_name]`
* `kubectl edit pod [pod_name]`

#### Deployments / Namespaces
* `kubectl edit deploy [deploy_name]`
* `kubectl delete deploy [deploy_name]`
* `kubectl expose deploy [deploy_name] --port=80 --type=NodePort`
* `kubectl scale deploy [deploy_name] --replicas=5`
* `kubectl delete ns`
* `kubectl edit ns [namespace_name]`

#### Services
* `kubectl edit svc [svc_name]`
* `kubectl delete svc [svc_name]`

#### DaemonSets
* `kubectl edit ds [ds_name] -n kube-system`
* `kubectl delete ds [ds_name]`

#### Service Accounts
* `kubectl edit sa [sa_name]`
* `kubectl delete sa [sa_name]`

#### Annotate
* `kubectl annotate po [pod_name] [annotation]`
* `kubectl annotate no [node_name]`

## Adding Resource
# Creating a Pod
* `kubectl create -f [name_of_file]`
* `kubectl apply -f [name_of_file]`
* `kubectl run [pod_name] --image=nginx --restart=Never`
* `kubectl run [pod_name] --generator=run-pod/v1 --image=nginx`
* `kubectl run [pod_name] --image=nginx --restart=Never`

# Creating a Service
* `kubectl create svc nodeport [svc_name] --tcp=8080:80`

# Creating a Deployment
* `kubectl create -f [name_of_file]`
* `kubectl apply -f [name_of_file]`
* `kubectl create deploy [deploy_name] --image=nginx`

# Interactive Pod
* `kubectl run [pod_name] --imange=busybox --rm -it --restart=Never -- sh`

# Out put YAML to a File
* `kubectl create deploy [deploy_name] --image=nginx --dry-run -o yaml > deploy.yaml`
* `kubectl get po [pod_name] -o yaml --export > pod.yaml`

# Getting Help
* `kubectl -h`
* `kubectl create -h`
* `kubectl run -h`
* `kubectl explain deploy.spec`

## Requests
# API Call
* `kubectl get --raw /apis/metrics.k8s.io/`

# Cluster Info
* `kubectl config`
* `kubectl cluster-info`
* `kubectl get componentstatuses`
