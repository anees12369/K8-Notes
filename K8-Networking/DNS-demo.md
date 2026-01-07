# **Demo to show how DNS works**

**1. Create two Deployments**

- One running Apache
- One running Nginx

**2. Exposed each Deployment as a Service `kubectl expose deployment nginx --port=80`**

- This automatically created DNS names for them

**3. Started a temporary debugging Pod**

- Tested communication using service names through `wget -q0 - <service-name>`

- From inside the Pod, you accessed: `apache`, `nginx`, `nginx.default`, `nginx.default.svc.cluster.local`

**Why all those names work**
---
- Kubernetes DNS automatically creates multiple DNS records for every Service: `service-name`
`service-name.namespace` `service-name.namespace.svc.cluster.local`

- This explains why: You don’t have to type the full DNS name as the Kubernetes DNS server searches all the domains: `default.svc.cluster.local`


