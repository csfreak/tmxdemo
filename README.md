# Application Samples
The home for Application samples, based on the open-cluster-management.io Subscription, Channel and Placement API

## Requirements
- `open-cluster-management.io` or Red Hat Advanced Cluster Management for Kubernetes.
- Clusters labelled as `development`, and `production`
```yaml
metadata:
  labels:
    usage: development
```
- All clusters with any `usage` label will get `helloworld` app.

# How to use
1. Add argocd application CR from deploy repo
```bash
oc apply -f deploy/app-deploy.yaml
```


