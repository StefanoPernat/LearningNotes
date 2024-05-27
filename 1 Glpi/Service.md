Here the [[Services]], for the future delete the name and the type if default

```yaml
apiVersion: v1
kind: Service
metadata:
  annotations:
  labels:
    run: glpiticketict
  name: glpiticketict
  namespace: ts
spec:
  ports:
  - name: port-1
    port: 80
    protocol: TCP
    targetPort: 80
  selector:
    run: glpiticketict
  type: ClusterIP
```
