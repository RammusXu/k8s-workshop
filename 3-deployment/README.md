## Apply
```
kubectl apply -f .
kubectl apply -f . --record

```

## Check status
```
kubectl get pod,deploy,svc
kubectl describe deploy demo-deployment
```

## Monitor logs
```
kubectl logs -f pod/demo-deployment-58d85cc65-h6g5b
curl localhost
```

## History
```
kubectl rollout history deployment demo-deployment
kubectl rollout status deployment demo-deployment
```

## Change deployment
```
kubectl scale deploy demo-deployment --replicas=4 --record
kubectl set image deployment/demo-deployment demo=jocatalin/kubernetes-bootcamp:v2 --record

kubectl rollout undo --dry-run=true deployment/demo-deployment
kubectl rollout undo deployment/demo-deployment
kubectl rollout undo --dry-run=true deployment/demo-deployment --to-revision=3
kubectl rollout undo deployment/demo-deployment --to-revision=3
```

## Clean
```
kubectl delete -f .
```