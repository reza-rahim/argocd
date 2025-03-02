# argocd

## https://argo-cd.readthedocs.io/en/stable/getting_started/

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


kubectl port-forward svc/argocd-server -n argocd 8080:443
argocd admin initial-password -n argocd

#kubectl create secret tls argo-cert  --key gke/tls/myserver.key  --cert gke/tls/myserver.crt 

#create helm based argocd application
kubectl apply -f nginx.yaml  -n argocd

#create helm based argocd application
kubectl apply -f helm-nginx-argo.yaml   -n argocd

argocd app list   


 kubectl apply -f helm-redis-argo-prod.yaml   -n argocd 


```

