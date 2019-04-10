## Install Docker Desktop for Mac
https://docs.docker.com/docker-for-mac/install/

```
docker ps
docker run hello-world
```

![docker-ps](https://github.com/RammusXu/k8s-workshop/blob/master/setup-environments/docker-ps.png)


## Install Kubernetes
可以使用 minikube or docker desktop

https://codefresh.io/kubernetes-tutorial/local-kubernetes-mac-minikube-vs-docker-desktop/

```
kubectl version
kubectl get nodes
kubectl cluster-info
kubectl config get-contexts

```

https://www.digitalocean.com/community/tutorials/how-to-install-software-on-kubernetes-clusters-with-the-helm-package-manager

## Install Helm
```
brew update && brew install kubernetes-helm
kubectl apply -f tiller-rbac.yaml
helm init --service-account tiller
```

```
helm version
```

```
helm install stable/kubernetes-dashboard --name kubernetes-dashboard --set rbac.clusterAdminRole=true
```

```
kubectl proxy
```

http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login
```
kubectl get secret
kubectl describe secret kubernetes-dashboard-token-rkq9g
```

## Troubleshooting
> Error: could not find tiller

沒有設定 tiller-rbac.yaml

> Error: could not find a ready tiller pod

等 tiller pod 起來

> 安裝 tiller 失敗時

砍掉重來
```
helm reset --force
kubectl apply -f tiller-rbac.yaml
helm init --service-account tiller
```
