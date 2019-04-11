## Apply
安裝 Ingress Controller
```
helm install --name nginx-ingress stable/nginx-ingress \
    --set controller.kind=DaemonSet \
    --set controller.hostNetwork=true \
    --set rbac.create=true

helm install --name nginx-ingress stable/nginx-ingress \
    --set controller.kind=DaemonSet \
    --set controller.hostNetwork=true \
    --set rbac.create=true \
    --namespace kube-system
```

```
kubectl apply -f .
```


## Check status
```
kubectl get ing
kubectl get pod,svc,deploy --namespace=kube-system
kubectl get pod,svc,deploy,ing
helm list
helm status nginx-ingress
```

## Demo
```
curl http://localhost
curl http://localhost/v1
curl http://localhost/v2
curl -H "Host:v1.com" http://localhost
curl -H "Host:v2.com" http://localhost
```

## Clean
```
kubectl delete -f .
```

## Why Ingress
1. 自動化 SSL (配合 helm: cert-manager)
2. Reverse Proxy
3. 一個 LB 集中管理
4. 可以用 regex

## Troubleshooting
>  spec.ports[0].nodePort: Forbidden: may not be used when `type` is 'ClusterIP'

砍掉重來
```
kubectl delete -f . && kubectl apply -f .
```

> curl http://localhost 出現 308 Permanent Redirect

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: my-ingress
  annotations:
    kubernetes.io/ingress.class: nginx
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
```


## Reference
https://medium.com/containerum/how-to-launch-nginx-ingress-and-cert-manager-in-kubernetes-55b182a80c8f
