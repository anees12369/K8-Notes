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