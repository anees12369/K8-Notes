# **Persistent Volumes**

- A piece of storage that's been set aside specifically for your applications and Kubernetes

- Your application doesn't need to worry about whether the storage is coming from a **local disk, an NFS server, or even cloud storage like AWS EBS or Google Persistent Disks**. You just know the storage is available and you can use it.

- They make it easy for your applications to use storage **without needing to know specifics of where that storage comes from or how it's managed.**

- Persistent volumes are typically created and managed by **cluster administrators**. They define these volumes with specific properties like **size, access modes, and storage class** and are used by pods 