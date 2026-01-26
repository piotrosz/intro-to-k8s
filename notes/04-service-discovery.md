# Service discovery

```PowerShell

kubectl create -f ./src/4.1-namespace.yaml

kubectl create -f ./src/4.2-data_tier.yaml -n service-discovery

kubectl describe service -n service-discovery data-tier

```