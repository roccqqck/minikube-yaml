# minikube-yaml

```
minikube config set driver docker
minikube start
```

```
minikube status
kubectl get all --all-namespaces
```

start dashboard
```
minikube dashboard
```




show nginx-app-service url
```
minikube service nginx-app-service --url
```


if service type:LoadBalancer
```
minikube tunnel
```
```minikube tunnel``` runs as a process, creating a network route on the host to the service CIDR of the cluster using the cluster’s IP address as a gateway. The tunnel command exposes the external IP directly to any program running on the host operating system.
```
Password:
Status:
 machine: minikube
 pid: 39087
 route: 10.96.0.0/12 -> 192.168.64.194
 minikube: Running
 services: [hello-minikube]
    errors:
  minikube: no errors
  router: no errors
  loadbalancer emulator: no errors
...
...
```



install ingress
```
minikube addons enable ingress
```
```
kubectl get ingress
```
```
NAME              CLASS    HOSTS              ADDRESS        PORTS   AGE
example-ingress   <none>   hello-world.info   172.17.0.15    80      38s
```
```
# /etc/hosts
172.17.0.15 hello-world.info
```


stop minikube
```
minikube stop
```

delete clean minikube
```
minikube delete
minikube delete --all
minikube delete --purge
```


