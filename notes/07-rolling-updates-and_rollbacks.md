# Rolling updates and rollbacks

- Rolling updates is default strategy - replicas are updated in groups.
- Alternative is recreate strategy (with downtime).
- Rollouts are triggered by Deployment template changes.

`kubectl rollout` - status, pause, resume, undo.

```PowerShell

kubectl edit -n deployments deployment app-tier

kubectl rollout -n deployments status deployment app-tier

```
