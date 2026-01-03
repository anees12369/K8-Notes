# **Storage**

- Pods are **ephemeral** = they can be created and destroyed frequently.

- Lets say your app/pod needs to **maintain its data** (like a database MYSQL app) 

- If that pod goes down, the data could vanish 

- However, **persistent storage** ensures that your data sticks around even if the pod gets destroyed. This way, when a new pod spins up, it can pick up right where it all left off, with all data intact. 

- This is critical for **stateful applications,** like **databases, message queues, or any app that needs to remember previous interactions/user data** 