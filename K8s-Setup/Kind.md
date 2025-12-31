# **kind**

- A tool that lets you run a local Kubernetes cluster on your own computer using Docker.

**How to setup a local cluster using kind:**
---
- Simple way: `kind create cluster` which creates a default cluster for you

- Or you can use a YAML config file to customize the cluster 

```yaml
# kind-config.yaml

kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker
```
- `kind create cluster --config kind-config.yaml`

- This creates: 1 control-plane node + 2 worker nodes

