
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