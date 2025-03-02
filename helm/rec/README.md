## https://redis.io/docs/latest/operate/kubernetes/deployment/quick-start/

```
kubectl create namespace  dev
kubectl create namespace  prod

VERSION=`curl --silent https://api.github.com/repos/RedisLabs/redis-enterprise-k8s-docs/releases/latest | grep tag_name | awk -F'"' '{print $4}'`

kubectl apply -n dev -f https://raw.githubusercontent.com/RedisLabs/redis-enterprise-k8s-docs/$VERSION/bundle.yaml
kubectl apply -n prod -f https://raw.githubusercontent.com/RedisLabs/redis-enterprise-k8s-docs/$VERSION/bundle.yaml

## helm create redis-chart 
helm install -n dev redis  ./redis-chart

helm list -n dev 

helm delete  redis -n dev 

## prod deployment
helm install -n prod redis  ./redis-chart  -f ./redis-chart/values.yaml -f ./redis-chart/values-prod.yaml
```
