# argocd

## https://argo-cd.readthedocs.io/en/stable/getting_started/

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

#kubectl create secret tls argo-cert  --key gke/tls/myserver.key  --cert gke/tls/myserver.crt 

kubectl apply -f nginx.yaml  -n argocd

argocd app list   

```
#kubectl apply -f nginx-app/nginx-deployment.yaml 
#kubectl apply -f nginx-app/nginx-service.yaml 
#kubectl delete  -f nginx-app/nginx-deployment.yaml 
#kubectl delete -f nginx-app/nginx-service.yaml 
```

```
kubectl config set-context --current --namespace=argocd
```
