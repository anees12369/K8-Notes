# **What are microservices?**

- Microservices are a way of building applications as many **small, independent services instead of one big application.**

- Each service: **Has its own code, Runs in its own container, Can be deployed and scaled independently and talks to others over APIs (HTTP/gRPC)** (e.g. cart service, payment service, user service)

- Containers allowed these microservices to be deployed on any environment, K8s allowed for management of these containers 

- Kubernetes: **Runs many small services efficiently + Handles scaling, restarts, and networking**