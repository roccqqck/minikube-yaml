reference

https://itnext.io/goodbye-docker-desktop-hello-minikube-3649f2a1c469

https://gist.github.com/protosam/11800faea25a3f89af9ece4f11c72f1d




```
brew install hyperkit minikube docker
```

```
minikube config set cpus 2
minikube config set memory 4g
```

```
minikube start --kubernetes-version=v1.19.14 --driver=hyperkit --container-runtime=docker
```

add env in .zshrc
```
# .zshrc
eval $(minikube docker-env)
```

check docker info
```
docker info
```
```
Client:
 Context:    default
 Debug Mode: false
Server:
 Containers: 14
  Running: 14
  Paused: 0
  Stopped: 0
 Images: 10
 Server Version: 20.10.8
 Storage Driver: overlay2
  Backing Filesystem: extfs
 ...
 ```
