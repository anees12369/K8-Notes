# **Deployments**

- A Deployment is a **Kubernetes object** used to run and manage pods

- You don’t usually create pods directly in real systems — you create deployments, and Kubernetes creates and manages the pods for you.

**What a Deployment Does**
---
- Creates a **ReplicaSet**

- Creates the desired number of pods through the **ReplicaSet**

- Recreates pods through **ReplicaSets** if they crash/get deleted (to the specified amount)

- Handles scaling, updates, and rollbacks

**Why Deployments Are Important**
---
- **Large-scale applications:** Multiple pods can be deployed instantly (e.g. web server may need multiple instances to handle traffic)

- **Automatic Healing**

- **Easy scaling:** Add/remove pods with config changes/commands 

- **Safe upgrades & rollbacks:** **Rolling updates** → update pods gradually, no downtime **Rollbacks** → instantly go back to a previous version if something breaks.

**Deployments vs ReplicaSet**
--- 
- When you create a Deployment, Kubernetes automatically creates a ReplicaSet for it.

- You generally don’t interact with the ReplicaSet directly when using Deployments; you manage the Deployment, and it handles **scaling, rolling updates, and recreating ReplicaSets as needed.**

**Deployment Yaml**
---
```yaml
apiVersion: apps/v1        # API version for deployments
kind: Deployment           # Kind specifies this is a Deployment
metadata:
  name: my-first-deployment
  labels:
    app: nginx
spec:
  replicas: 3              # Number of pod copies
  selector:
    matchLabels:
      app: nginx           # Connects deployment to the correct pods
  template:
    metadata:
      labels:
        app: nginx         # Labels for the pods themselves
    spec:
      containers:
      - name: nginx
        image: nginx:latest
```
- `replicas:` How many replicas of pods you want to run

- `selector:` Ensures the Deployment manages only the pods it created through `matchLabels`

**Pod level**

- `template:` A blueprint/spec for the **pods**, anything nested within this = pod related
 
 * `metadata.labels:` Labels that link pods back to the Deployment via the selector.

 * `spec.containers:` Container definitions, just like in a standalone pod YAML.

- Pods are named after the Deployment, with unique identifiers, e.g., `my-first-deployment-7d8f5c6f9b-abcde`

