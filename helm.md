
## Start with Helm
```
helm install stable/wordpress --name wordpress --set resources.requests.cpu=100m
helm delete wordpress
helm delete wordpress --purge
```

> 0/1 nodes are available: 1 Insufficient cpu.

> pod has unbound PersistentVolumeClaims Back-off restarting failed container