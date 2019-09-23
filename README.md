# Kubernetes Cheat Sheet

## Kubectl Cheat Sheet

- [`kubernetes.io`](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [`github.com/dennyzhang`](https://github.com/dennyzhang/cheatsheet-kubernetes-A4)
- [`linuxacademy.com`](https://linuxacademy.com/blog/containers/kubernetes-cheat-sheet/)

## Kubeadm Certificate

Certificate Path                                 | CN Name                       | Organization   | Issuer
------------------------------------------------ | ----------------------------- | -------------- | ----------
/etc/kubernetes/pki/apiserver.crt                | kube-apiserver                |                | kubernetes
/etc/kubernetes/pki/apiserver.key                |                               |                |
/etc/kubernetes/pki/ca.crt                       | kubernetes                    |                | kubernetes
/etc/kubernetes/pki/apiserver-kubelet-client.crt | kube-apiserver-kubelet-client | system:masters | kubernetes
/etc/kubernetes/pki/apiserver-kubelet-client.key |                               |                |
/etc/kubernetes/pki/apiserver-etcd-client.crt    | kube-apiserver-etcd-client    | system:masters | self
/etc/kubernetes/pki/apiserver-etcd-client.key    |                               |                |
/etc/kubernetes/pki/etcd/ca.crt                  | kubernetes                    |                | kubernetes

- [`PKI certificates and requirements`](https://kubernetes.io/docs/setup/best-practices/certificates/)
