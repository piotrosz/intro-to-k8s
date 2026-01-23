One or more containers in Pod
All Pods share cluster network
1 IP address per Pod

```PowerShell
kubectl get pods

kubectl create -f ./src/1.1-basic_pod.yaml 

kubectl describe pod mypod | more

kubectl delete pod mypod

kubectl create -f ./src/1.2-port_pod.yaml 

kubectl delete pod mypod

kubectl create -f ./src/1.4-resources_pod.yaml 
```