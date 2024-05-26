A **Replica Set**'s purpose is to maintain a stable set of [[Pods]] running at any given time. It is often used to guarantee the availability of a specified number of identical [[Pods]].

**Replica Sets should never be managed by people, Kubernetes does this for you**

### Useful commands to know

`k get replicasets` display all **Replica Sets**
`k describe replicasets.apps test-584468bd69` describe the specified **Replica Set**
