## Apply
```
kubectl apply -f .
```

## Demo
```
kubectl get pod,configmap,secret
kubectl describe configmap/my-config
kubectl describe secret/my-secret
kubectl exec -it demo-deployment-6d484f466-wwv88 -- bash
```

```
echo -n 'rammuspass' | base64
echo 'cmFtbXVzcGFzcw==' | base64 --decode
```

## Clean
```
kubectl delete -f .
```