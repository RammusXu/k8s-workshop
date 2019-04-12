## Install Docker Desktop for Mac
https://docs.docker.com/docker-for-mac/install/

```
docker ps
docker run -it --rm hello-world
```

![docker-ps](https://github.com/RammusXu/k8s-workshop/blob/master/1-setup-environments/docker-ps.png?raw=true)


## Install Kubernetes
可以使用 minikube or docker desktop

https://codefresh.io/kubernetes-tutorial/local-kubernetes-mac-minikube-vs-docker-desktop/

```
kubectl version
kubectl get nodes
kubectl cluster-info
kubectl config get-contexts
kubectl get pod --namespace=kube-system
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

## Troubleshooting
> Error: could not find tiller

沒有設定 tiller-rbac.yaml

或是還在 creating

> Error: could not find a ready tiller pod

等 tiller pod 起來

> 安裝 tiller 失敗時

砍掉重來
```
helm reset --force
kubectl apply -f tiller-rbac.yaml
helm init --service-account tiller
```
