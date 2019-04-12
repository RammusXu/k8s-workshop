```
kubectl apply -f hello-pod.yaml 
kubectl get pod
kubectl describe pod/hello-pod
```

```
kubectl logs hello-pod | tail -n3
kubectl logs -f hello-pod
```

```
curl http://localhost:8099/
```

```
kubectl apply -f hello-service.yaml
kubectl get svc
kubectl describe svc/helloworld-service
```


Clear
```
kubectl delete -f .
```


## Troubleshooting

> curl: (52) Empty reply from server

確認 service targetPort 是否正確指向 pod containerPort


## Reference
- Kubernetes的三种外部访问方式：NodePort、LoadBalancer 和 Ingress dockone.io/article/4884