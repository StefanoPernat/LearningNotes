[[0 Kubernetes/Ingress|Ingress]] basic structure

```yaml
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  annotations:
    nginx.ingress.kubernetes.io/affinity: cookie
    nginx.ingress.kubernetes.io/affinity-mode: persistent
    nginx.ingress.kubernetes.io/session-cookie-expires: "172800"
    nginx.ingress.kubernetes.io/session-cookie-max-age: "172800"
    nginx.ingress.kubernetes.io/session-cookie-name: routeglpiticketict
    nginx.ingress.kubernetes.io/use-forwarded-headers: "true"
  name: glpiticketict
  namespace: ts
spec:
  rules:
  - host: <host>
    http:
      paths:
      - backend:
          serviceName: glpiticketict
          servicePort: 80
        path: /
        pathType: ImplementationSpecific
```