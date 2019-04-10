# k8s-workshop
自己的 k8s 學習筆記和幫助新人上手的 workshop

[setup-environments](https://github.com/RammusXu/k8s-workshop/blob/master/setup-environments/README.md)


## Course
https://github.com/wardviaene/kubernetes-course
https://github.com/wardviaene/advanced-kubernetes-course
https://github.com/wardviaene/on-prem-or-cloud-agnostic-kubernetes

## TODO
- DNS

    foo.bar.my-namespace.svc.cluster.local

- kube-system
    - cert-manager
    - kubenetes-dashboard

- Why Ingress
    1. 自動化 SSL
    2. Reverse Proxy
    3. 一個 LB 集中管理
    4. 可以用 regex
- kops
    ```
    brew update && brew install kops
    ```