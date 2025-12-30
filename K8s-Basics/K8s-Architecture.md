# **K8s Architecture** 

![alt text](../Screenshots/image-1.png)

**Cluster**
---
- A cluster is a **group of nodes** that Kubernetes uses to run applications. Provides **CPU, memory, storage, and networking**

- Can run on cloud platforms like **EKS (AWS), AKS (Azure), GKE (Google)**

- Kubernetes uses the cluster’s resources to run **workloads (apps)**

- Think of a cluster as the entire system (e.g. Master node + Worker nodes)

**Nodes (The Machines)**
---
- A node (or minion) is a single machine: can be a virtual machine or a physical server

**There are two types of nodes:**

- **Master Node (Control Plane)** → brain
- **Worker Nodes** → muscles

**The Master Node**
---
- The master node controls the entire cluster,it **does not** run your application containers. Instead, **it decides what should run and where.**

- Can consist of multiple machines

**Key Components of the Master Node** 

- **kube-api-server** - The entry point to Kubernetes = communication hub - All commands go through this (kubectl, CI/CD, etc.) - e.g. 'deploy this app'

- **etcd** - Kubernetes’ memory - Stores: **Cluster state, Configuration, What should be running and where** - If something crashes, Kubernetes checks etcd to recover.

- **kube-controller-manager** - The supervisor - Makes sure **the desired state matches the actual state** (e.g. You want 3 pods, One crashes, Controller creates a new one)

- **kube-scheduler** - Decides which worker node a new pod should run on - Considers: **Available CPU + memory and other rules (affinity, taints, etc.)**

- **cloud-controller-manager (cloud only)** - Connects Kubernetes to the cloud provider - **Manages: Load balancers, Storage volumes, Networking resources**

**Worker Nodes**
---
- Worker nodes are where your applications actually run.

**Each worker node contains:**

- **kubelet** - An agent running on each node which communicates with the master node - Ensures pods are running as instructed - Starts, stops, and monitors containers - `*Run this pod* → kubelet makes it happen.

- **kube-proxy** - Handles networking - Allows pods to: **Talk to each other, Access services, Manages routing and load balancing inside the cluster**

- **Pods** - Smallest unit in Kubernetes - A pod: **Wraps one or more containers and is what Kubernetes deploys and manages** - They use the resources (CPU, RAM etc) of the worker node

**How It All Works Together:**
---

1. You deploy an app

2. kube-api-server receives the request

3. Scheduler decides where to run it

4. Controller-manager ensures the desired state

5. kubelet on the worker node runs the pod

6. kube-proxy enables networking