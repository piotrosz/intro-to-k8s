# Service discovery

## Namespaces

- no nesting
- logical separation
- can communicate with each other
- default namespace
- RBAC
- separate dev, test

## Why services?

- Support for multi-pod (multi-tier) design.
- Handles change of Pod IP address.
- Can load balance traffic to Pods.

- service has endpoint corresponding to selected pod
- ClusterIP service for internal-only access (within the cluster)

### Environment variables

- service adress is automatically injected in containers as env var.
- env variables follow naming conventions based on service name (HOST, PORT).
- only set at container startup

### DNS

- DNS records created in cluster's DNS based on service name
- Containers are automatically configured to query cluster DNS

Env variables and DNS allows Pods to discover Services.

### Example

(Support tier (Counter & Poller)) pod <-> App tier service <-> Server pod <-> Data tier service <-> Redis pod

```PowerShell

kubectl create -f ./src/4.1-namespace.yaml

kubectl create -f ./src/4.2-data_tier.yaml -n service-discovery

kubectl get pod -n service-discovery

kubectl describe service -n service-discovery data-tier

kubectl create -f ./src/4.3-app_tier.yaml -n service-discovery

kubectl create -f ./src/4.4-support_tier.yaml -n service-discovery

kubectl logs -n dervice-discovery support-tier poller -f

```
