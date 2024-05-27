# What is a Pod

A pod is the smallest entity in a **Kubernetes** cluster

![what is a Pod](pictures/What-is-a-Pod.png)

A pod is not a container, but a collection of containers + other resources

- **Pods** are ephemeral. You should not expect a Pod to have a long lifespan.
- **Pods** are constantly changing and be moved across nodes.
- How will the system keep track of the constantly changing IP addresses?
### Kubectl commands to know

`k edit pod nginx` it allows to edit a pod manifest
`k exec -it <name> -- /bin/bash or /bin/sh` exec into a pod
`k run nginx-step --image=nginx --dry-run=client -o yaml > nginx-step.yaml` It allows you to have the basic template of a pod in nginx-step.yaml
`k describe pod nginx` describe the specified pod

