# Autoscaling

- CPU utilization or other custom metrics
- Pods must have CPU requests
- Autoscaler: horizontalPolAutoscaler (hpa) is configured with target CPU and min and max replicas

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

# To get a list of short notations 
kubectl api-resources
# hpa = horizontalpodautoscalers

kubectl describe -n deployments hpa
kubectl get -n deployments hpa

# this will open editor and then apply changes
kubectl edit -n deployments hpa
```
