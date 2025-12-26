# **What problem did K8s want to resolve?**

- A **node** is a computer (physical or virtual) that is used to run containers.

-  Let's say, for example, we have a container  and deploy it to a **node,** which has **4GB RAM and 2 cores.** 

- So if we have an increase of more users accessing our application, we create **another node** running the same app

- Now, if the developers make changes to the application and they push it as a new container image, we now have version 1.2. We now have to create a **new node** before destroying version 1.1.

- So now we has an issue: we have 3 nodes = **6 cores and 12GB of RAM for just 3 containers**

- This is where Kubernetes comes into play: Kubernetes will use a single node and fill it up with as many pods as possible. Rather than having one container per node.


