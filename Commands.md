# Kubernetes (kubectl) Cheat Sheet

A beginner-friendly, practical reference for working with Kubernetes using `kubectl`.

---

## Cluster & Context

Check cluster information:

```bash
kubectl cluster-info
```

List available contexts:

```bash
kubectl config get-contexts
```

Show current context:

```bash
kubectl config current-context
```

Switch context:

```bash
kubectl config use-context <context-name>
```

---

## Nodes

List nodes:

```bash
kubectl get nodes
```

Describe a node:

```bash
kubectl describe node <node-name>
```

---

## Pods

List pods:

```bash
kubectl get pods
```

List pods with more details:

```bash
kubectl get pods -o wide
```

Describe a pod:

```bash
kubectl describe pod <pod-name>
```

Delete a pod:

```bash
kubectl delete pod <pod-name>
```

Watch pods in real time:

```bash
kubectl get pods -w
```

---

## Deployments

List deployments:

```bash
kubectl get deployments
```

Describe a deployment:

```bash
kubectl describe deployment <deployment-name>
```

Delete a deployment:

```bash
kubectl delete deployment <deployment-name>
```

Scale a deployment:

```bash
kubectl scale deployment <deployment-name> --replicas=3
```

---

## Rollouts & Updates

Check rollout status:

```bash
kubectl rollout status deployment <deployment-name>
```

View rollout history:

```bash
kubectl rollout history deployment <deployment-name>
```

Rollback deployment:

```bash
kubectl rollout undo deployment <deployment-name>
```

---

## Services

List services:

```bash
kubectl get services
```

Describe a service:

```bash
kubectl describe service <service-name>
```

Delete a service:

```bash
kubectl delete service <service-name>
```

Expose a deployment:

```bash
kubectl expose deployment <deployment-name> --type=NodePort --port=80
```

---

## Apply & Manage YAML

Apply a YAML file:

```bash
kubectl apply -f file.yaml
```

Delete resources from YAML:

```bash
kubectl delete -f file.yaml
```

Apply all YAML files in a folder:

```bash
kubectl apply -f .
```

---

## Namespaces

List namespaces:

```bash
kubectl get namespaces
```

Create a namespace:

```bash
kubectl create namespace <name>
```

Delete a namespace:

```bash
kubectl delete namespace <name>
```

Get resources in a namespace:

```bash
kubectl get pods -n <namespace>
```

---

## Logs & Debugging

View pod logs:

```bash
kubectl logs <pod-name>
```

Logs from a specific container:

```bash
kubectl logs <pod-name> -c <container-name>
```

Stream logs:

```bash
kubectl logs -f <pod-name>
```

---

## Exec Into a Pod

Open a shell inside a pod:

```bash
kubectl exec -it <pod-name> -- /bin/sh
```

If bash is available:

```bash
kubectl exec -it <pod-name> -- /bin/bash
```

---

## Cleanup

Delete all pods:

```bash
kubectl delete pods --all
```

Delete all resources in a namespace:

```bash
kubectl delete all --all -n <namespace>
```

---

## Quick Info Commands

Get everything:

```bash
kubectl get all
```

Describe everything:

```bash
kubectl describe all
```
Cluster name:
```bash
kubectl config current-context
```
---

## Quick Test Commands

Run a test pod:

```bash
kubectl run nginx --image=nginx
```

Create a deployment:

```bash
kubectl create deployment nginx --image=nginx
```

---

## Useful Flags

```bash
-n <namespace>     # specify namespace
-o wide            # extended output
-o yaml            # output as YAML
--dry-run=client   # test without applying
```

Example:

```bash
kubectl get pod nginx -o yaml
```

---

## Mental Model

* kubectl → talks to the cluster
* Pods → smallest unit
* Deployments → manage pods
* Services → networking
* YAML → desired state

---

## Key Takeaway

kubectl is your primary interface to Kubernetes. These commands cover the majority of daily Kubernetes operations.

- `kubectl exec` lets you run commands inside a running Pod