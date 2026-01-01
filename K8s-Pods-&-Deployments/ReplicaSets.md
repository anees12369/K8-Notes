# **ReplicaSets vs Deployments**

- A ReplicaSet ensures that a **specified number of identical pods** are running at any given time.

- A Deployment manages ReplicaSets for you and adds powerful features such as: **Rolling updates, Rollbacks, Version history, Safer application upgrades with no downtime**

**If you deploy a new version of your app:**
---

- The Deployment creates a new ReplicaSet for the new version.

- The old ReplicaSet is gradually scaled down. The new ReplicaSet is gradually scaled up.

- This allows: Rolling updates (no downtime) + Easy rollbacks if something goes wrong