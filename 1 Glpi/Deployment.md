The following are the [[Deployments]] manifest, as I learned from the **Kubernetes Fundamentals Course** By Misha, I found it not 100% correct, I like the label stucture for the networking rules,  remember too keep it in the new [[Cluster]].

I like to use the default label **app** instead of the run like now.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  annotations:
  labels:
    run: glpiticketict
  name: glpiticketict
  namespace: ts
spec:
  replicas: 2
  selector:
    matchLabels:
      run: glpiticketict
  template:
    metadata:
      labels:
        networking/allow-dbts: "true"
        networking/allow-email-smtp: "true"
        networking/allow-internet-egress: "true"
        networking/allow-ldap: "true"
        networking/allow-mydb: "true"
        run: glpiticketict
      namespace: ts
    spec:
      containers:
      - env:
        - name: TZ
          value: Europe/Rome
        image: dr.trentinosviluppo.it/glpi
        imagePullPolicy: Always
        name: glpiticketict
        ports:
        - containerPort: 80
          protocol: TCP
        resources:
          limits:
            memory: 1Gi
          requests:
            memory: 512Mi
        volumeMounts:
        - mountPath: /var/www/html/glpi
          name: glpiticketict-pvc
      dnsPolicy: ClusterFirst
      imagePullSecrets:
      - name: promregistry
      restartPolicy: Always
      volumes:
      - name: glpiticketict-pvc
        persistentVolumeClaim:
          claimName: glpiticketict-pvc
```
