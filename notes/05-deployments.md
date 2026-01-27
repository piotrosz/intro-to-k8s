# Deployments

- Represents multiple replicas of a Pod
- Describes desired state
- Horizontal scaling -> Pods must be stateless!

```PowerShell
kubectl create -f ./src/5.1-namespace.yaml

diff -y ./src/4.2-data_tier.yaml ./src/5.2-data_tier.yaml

kubectl create -n deployments -f ./src/5.2-data_tier.yaml -f ./src/5.3-app_tier.yaml -f ./src/5.4-support_tier.yaml

kubectl get -n deployments deployments

kubectl get -n deployments pods

kubectl scale -n deployments deployments support-tier --replicas=3

kubectl delete -n deployments pods support-tier-74c4d75698-v8cfz support-tier-74c4d75698-fm2t8

kubectl scale -n deployments deployments app-tier --replicas 3

kubectl describe -n deployments service app-tier
``
