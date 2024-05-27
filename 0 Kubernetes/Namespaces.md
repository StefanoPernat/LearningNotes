A **namespace** is a logical group of resources, for production cluster consider *not* to use the default namespace, make new ones and use those.

**Every application or workload** needs to have his namespace.

### Useful commands to know

`k create namespace <name>` create the specified namespace
`k get namespaces` list all namespaces
`k config set-context --current --namespace=<name>` change the default namespace in the current context
