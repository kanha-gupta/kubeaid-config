# KubeAid Config

A template repository for your KubeAid instance configuration.

## Managed Kubernetes Clusters (`/k8s`)

Provides examples and configuration for managed clusters.

### Example: [test.cluster.com](https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com)

- **Cluster Name**: `test.cluster.com`
- **Services**: Determined by [ArgoCD App Templates](https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com/argocd-apps/templates).
- **Configuration**: Service settings defined in [ArgoCD Apps](https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com/argocd-apps).
- **Bootstrap**: Cluster spin-up/recovery configuration via `kubeaid-bootstrap-general.yaml` in the [cluster directory](https://github.com/Obmondo/kubeaid-config/tree/main/k8s/test.cluster.com).

Documentation for natively supported apps is available in the [KubeAid repository](https://github.com/Obmondo/kubeaid/tree/master/argocd-helm-charts) (e.g., [CloudNativePG](https://github.com/Obmondo/kubeaid/tree/master/argocd-helm-charts/cloudnative-pg)).

## Kube Prometheus Mixins

Enable or disable support mixins in your cluster Jsonnet file (`k8id-config`).
Manually rebuild the YAML file after changes:

```sh
./build/kube-prometheus/build.sh /path/to/k8id-config/k8s/<cluster-name>
```

Commit and push changes, then prune in ArgoCD if mixins were removed.
