# Intro

[Pod, Node, Cluster](https://www.cloudzero.com/blog/kubernetes-node-vs-pod/#:~:text=A%20node%20is%20a%20worker,managed%20collectively%20within%20a%20node.)

## Pods

- One or more containers in Pod
- All Pods share cluster network
- 1 IP address per Pod

```PowerShell
kubectl get pods

kubectl create -f ./src/1.1-basic_pod.yaml 

kubectl describe pod mypod | more

kubectl delete pod mypod

kubectl create -f ./src/1.2-port_pod.yaml 

kubectl delete pod mypod

kubectl create -f ./src/1.4-resources_pod.yaml 
```