## Setting up Nginx Ingress
#### Nginx ingress helm chart
```
helm install --name nginx-ingress stable/nginx-ingress
```
#### Example ingress
```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  annotations:
    kubernetes.io/ingress.class: nginx
  name: example
  namespace: foo
spec:
  rules:
    - host: www.example.com
      http:
        paths:
          - backend:
              serviceName: exampleService
              servicePort: 80
            path: /
  # This section is only required if TLS is to be enabled for the Ingress
  tls:
      - hosts:
          - www.example.com
        secretName: example-tls

```
#### Create secret for TLS
```
kubectl create secret tls ingress-tls \
    --key ingress-tls.key \
    --cert ingress-tls.crt
```
