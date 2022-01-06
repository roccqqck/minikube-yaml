# minikube-yaml

reference

https://minikube.sigs.k8s.io/docs/handbook/config/

https://minikube.sigs.k8s.io/docs/drivers/


```
minikube config set driver docker
minikube config set container-runtime docker
minikube config set cpus 2
minikube config set memory 4g
minikube start
```
or
```
minikube start --kubernetes-version=v1.19.14 --driver=hyperkit --container-runtime=containerd
```

```
minikube status
kubectl get all --all-namespaces
```

start dashboard
```
minikube dashboard
```




## show nginx-app-service url
```
minikube service nginx-app-service --url
```

or use kubectl port-forward
```
kubectl get svc    
```       
```                          
NAME                TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)    AGE
nginx-app-service   ClusterIP   10.101.246.134   <none>        8080/TCP   78m
```
```
kubectl port-forward svc/nginx-app-service 8081:8080
```
http://localhost:8081



## if service type:LoadBalancer
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



## install ingress
```
minikube addons enable ingress
```
```
After the addon is enabled, please run "minikube tunnel" and your ingress resources would be available at "172.17.0.15"
```
check ingress
```
kubectl get ingress
```
```
NAME              CLASS    HOSTS              ADDRESS        PORTS   AGE
example-ingress   <none>   hello-world.info   172.17.0.15    80      38s
```
edit /etc/hosts
```
# /etc/hosts
172.17.0.15 hello-world.info
```


show minikube images
```
minikube image list
```

Create a second cluster
```
minikube start -p ClusterName
```

show minikube clusters list
```
minikube profile list
```

change minikube profile cluster
```
minikube profile default
minikube profile ClusterName
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


