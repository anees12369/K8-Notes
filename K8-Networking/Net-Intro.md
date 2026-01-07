# **Basics of K8 Networking**

- Pods can communicate with each other without needing any complex network setups like a NAT

- Every pod has a **unique, single, and consistent IP address,** they talk to each other directly using those IPs

- **All nodes can communicate with all pods without using NAT as well,** regardless of whether the pod is running.

- This means you don't have to worry about setting up complicated networking rules or translations

- It can get more advanced when you have **network policies and you specify different networking.** 