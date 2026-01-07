# **Service Discovery + DNS**

- In Kubernetes, **service discovery and DNS** are what let Pods and Services find each other by **name** instead of IP address. 

- Kubernetes handles it automatically, 

**Every time you create a Service, Kubernetes automatically creates a DNS entry for it. This means:**

- Pods don’t need to know IP addresses

- They can just use service names like `backend-service`

- When traffic is sent to a service name, **Kubernetes DNS resolves that name to the correct Service IP**, and the **Service then routes traffic to the right Pods.**

**Understanding this is important because:**

- IPs change, names don’t

- Most connectivity issues are actually DNS or Service issues

- Knowing how DNS works makes debugging much easier

**In the labs, you’ll see:**

- How Services get DNS names

- How Pods resolve those names

- How Services communicate using DNS instead of IPs


