**Helm** is the packet manager for Kubernetes.

It lives on your local pc, not in the cluster

### Installation

```bash
 brew install helm
```

### Deploying an app via helm example

```bash
helm repo add oben01 https://oben01.github.io/charts/
helm repo update
helm install homarr oben01/homarr --namespace homarr --create-namespace
```

### Uninstall 
```bash
helm uninstall -n homarr homarr
```

### Use custom values

```bash
helm install homarr oben01/homarr --namespace homarr --create-namespace --values=values.yaml
```

### Upgrade example
```bash
helm upgrade prometheus-stack  prometheus-community/kube-prometheus-stack -n monitoring --values values.yaml
```
