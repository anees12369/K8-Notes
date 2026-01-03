# **Service Config Demo**

```yaml 
# Config for deployment
---
apiVersion: v1
kind: Service
metadata:
  name: nginx-svc
spec:
  type: ClusterIP
  selector:
    app: nginx
  ports:
  - protocol: TCP
    port: 80 # Thd port of your service 
    targetPort: 80 #The port of your pod 
```
- How to access your service locally: `kubectl port-forward svc/service-name 8080:serviceport`