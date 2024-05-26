A **Service** offers a consistent address to access a set of [[Pods]].

A **Service** is a method for exposing a network application that is running as one or more [Pods](https://kubernetes.io/docs/concepts/workloads/pods/) in your cluster.
### Type of Services

**ClusterIP**: Default, create a cluster-wide IP for the service.
**NodePort**: Exposes a port on each node allowing direct access to the service through any node's IP address. (Try to avoid)
**LoadBalancer**: Used for cloud providers, (can also be used in k3s/rancher desktop)
#### Load Balancer
Gives you an external IP like the following:

![Load Balancer](Pictures/Load-Balancer.jpg)

This is the suggested way to expose your application when working inside the **home lab**.
### Useful commands to know
`k get services` list all available services
`k delete svc -n <namespace> <name>` delete the specified service.
`k expose deployment <name> --port=9000` create a service for a deployment (to use **NOT IN PRODUCTION**)
`k get services <name> -o yaml` get the YAML of a service