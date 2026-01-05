# **Persistent Volume Chain**

-  **How do applications actually use PVs?** PVC = a request that your application makes to the cluster saying I need some storage.

- PVCs are the bridge between your application and the matching PV/storage resources in the cluster 

- When you define a PVC, **you specify the amount of storage you need and any other requirements like access modes**. The cluster then looks for a PV, that matches your request and binds it to the PVC.
