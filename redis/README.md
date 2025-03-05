https://redis.io/docs/latest/operate/kubernetes/deployment/quick-start/

kubectl create namespace dev
kubectl create namespace prod

export VERSION=`curl --silent https://api.github.com/repos/RedisLabs/redis-enterprise-k8s-docs/releases/latest | grep tag_name | awk -F'"' '{print $4}'`

kubectl apply -n dev -f https://raw.githubusercontent.com/RedisLabs/redis-enterprise-k8s-docs/$VERSION/bundle.yaml
kubectl apply -n pod  -f https://raw.githubusercontent.com/RedisLabs/redis-enterprise-k8s-docs/$VERSION/bundle.yaml


kubectl apply -n dev -f rec.yaml

kubectl port-forward -n dev svc/my-rec-ui  8443:8443  &

kubectl get -n dev secrets my-rec -o json | jq .data.password | sed 's/"//g' | base64 -d
kubectl get -n dev secrets my-rec -o json | jq .data.username  | sed 's/"//g' | base64 -d 
