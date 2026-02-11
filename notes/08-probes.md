# Probes

- healhcheck

- readiness probes
- liveness probes

```PowerShell
kubectl create -f ./src/7.1-namespace.yaml

kubectl create -f ./src/7.2-data_tier.yaml -n probes

kubectl get deployments -n probes -w

kubectl create -f ./src/7.3-app_tier.yaml -n probes

kubectl get deployments -n probes app-tier -w

kubectl get -n probes pods

kubectl logs -n probes [pod-name]
```
