# **Config Maps**

**What problem do ConfigMaps solve?**
---
- Your app needs settings to run: URLs, Environment variables, File paths, Feature flags

- You don’t want to hard-code these into your app because: They change between environments (dev, test, prod) + You’d have to rebuild your app every time

- That’s where ConfigMaps come in.

**What is a ConfigMap?**
---
- A ConfigMap is a place to store **non-secret configuration data** for your application.

- For example: instead of hardcoding: `DATABASE_URL=prod-db.example.com` you put it in a ConfigMap 

**Why ConfigMaps are useful**
---
- Same app image works everywhere

- Change configuration without changing code

- Pods always start with the correct settings

- PVs/PVCs store data, ConfigMaps store settings.

**Config Map Demo**
---
**Creating a ConfigMap:** 
- `kubectl create cofigmap <name> --from-literal=ENV_VAR_1= --from-literal=ENV_VAR_2=`

- `-from-literal=ENV_VAR_1=` a way to parse an env var 

**Creating a pod that uses the ConfigMap**

```yaml
# cmap-pod.yaml

apiVersion: v1
kind: Pod
metadata:
  name: cm-demo
spec:
  containers:
  - name: demo-container
    image: busybox
    command: ["/bin/sh", "-c", "env && sleep 3600"]

    # Setting ENV VARs from the ConfigMap
    env:
    - name: APP_COLOUR
      valueFrom:
        configMapKeyRef:
          name: my-cmap
          key: APP_COLOUR
    - name: APP_MODE
      valueFrom:
        configMapKeyRef:
          name: my-cmap
          key: APP_MODE

    volumeMounts:
    - name: config-volume
      mountPath: /etc/config

  volumes:
  - name: config-volume
    configMap:
      name: my-cmap
```
- **Volume mounts** expose ConfigMap data **as files** inside the container.

- **Env vars** = someone telling you the settings once

- **Volume mount** = a settings folder you can open anytime
