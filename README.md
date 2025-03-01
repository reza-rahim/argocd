# argocd

## https://argo-cd.readthedocs.io/en/stable/getting_started/

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

#kubectl create secret tls argo-cert  --key gke/tls/myserver.key  --cert gke/tls/myserver.crt 

#create helm based argocd application
kubectl apply -f nginx.yaml  -n argocd

#create helm based argocd application
kubectl apply -f helm-nginx-argo.yaml   -n argocd

argocd app list   

```

```
kubectl config set-context --current --namespace=argocd
```
