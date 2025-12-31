# **Deployments**

- A Deployment is a **Kubernetes object** used to run and manage pods

- You don’t usually create pods directly in real systems — you create deployments, and Kubernetes creates and manages the pods for you.

**What a Deployment Does**
---
- Creates pods
- Ensures the right number of pods are always running by recreating pods if they crash or are deleted through **ReplicaSets**
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

