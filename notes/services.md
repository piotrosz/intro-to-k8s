Service defines networking rules for accessing Pods within the cluster AND from the internet.

Use labels to select a group of Pods.

Has a fixed IP address

Distributes access to group od Pods

```PowerShell
kubectl create -f ./src/2.1-web_service.yaml

kubectl get service webserver

kubectl describe nodes | grep -i address -A 1
```

