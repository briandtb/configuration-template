# Kind with 1 master and 2 nodes
The assets include metrics-server configuration. So you can use resources like horizontalpodautoscalers.autoscaling, ...
> The `components.yaml` configuration worked with kind version `kind v0.9.0 go1.15.2 linux/amd64`. For other versions, upper or below, I'm not sure that it works.
## Reference link
- [Quick Start](https://kind.sigs.k8s.io/docs/user/quick-start/)
- [Workaround for metrics-server](https://github.com/kubernetes-sigs/kind/issues/398)
## How to run 
```make create```
## Apply metrics-server
```make metrics-server```
## Delete 
```make delete```
