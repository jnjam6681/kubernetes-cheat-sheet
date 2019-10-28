## Secrets
#### Encode data before store
```
echo -n 'hello' | base64
```
#### Decode secrets
```
echo -n 'glhs4='' | base64 —-decode
```
#### Build secrets form env file
```
kubectl create secret generic my-secret --from-env-file=.env
```
#### Update secrets
```
kubectl create secret generic laravel --from-env-file=.env --dry-run -o yaml | kubectl apply -f -
```
