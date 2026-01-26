# Multi container pods

```PowerShell
kubectl create -f ./src/3.1-namespace.yaml

kubectl get namespace

kubectl create -f ./src/3.2-multi_container.yaml -n microservice

kubectl get -n microservice pod app

kubectl logs -p app -c poller -n microservice --tail 


```
