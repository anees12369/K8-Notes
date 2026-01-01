# **Into into K8s Services**

- Imagine your application has different groups of pods running in different areas.

- One group handles the front-end, another takes care of the back-end, and the other group manages the database. 

- Services allow for **seamless connectivity between these groups of pods** 
 
- They connect the right pods to each other without you having to worry about the specifics of networking

**Why are services important?**
---
- Services are crucial because they allow different parts of your application at the front-end, the back-end, the database to work independently, making your app more modular and easy to manage.

**How do services identify pods?**
---
- Service use labels to identify pods e.g. `app: nginx` `app: frontend`

**Different types of services:**
---
- **ClusterIP** (default) → Pods talk to each other through an internal IP address

- **NodePort** → Exposes the service **on a specific port on each node in your cluster**

- **LoadBalancer** → Creates an external load balancer which distributes traffic to your pods 

**Networking Behind the Scenes** 
---
- Services operate at Layer 4 (Transport Layer) of the OSI model - TCP / UDP traffic 

- `kube-proxy` handles traffic routing.

