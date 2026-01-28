# Autoscaling

- CPU utilization or other custom metrics

```PowerShell

kubectl apply -f ./src/metrics-server/

kubectl top pods -n deployments

diff -y ./src/5.3-app_tier.yaml ./src/6.1-app_tier_cpu_request.yaml

# This fails because resources exist
kubectl create -f 6.1-app_tier_cpu_request.yaml -n deployments

# Use apply instead
kubectl apply -f 6.1-app_tier_cpu_request.yaml -n deployments

kubectl get -n deployments deployments app-tier

kubectl create -n deployments -f ./src/6.2-autoscale.yaml
```
