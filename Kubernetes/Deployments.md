You **describe** a *desired state* in a **Deployment**, and the *Deployment Controller* changes the actual to the desired state. You can define **Deployment** to create new [[Replica Set]] or to remove existing Deployments.

**I want this 10 pods to run the whole time**

### Strategy

```yaml
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
```

It can be percentage or numbers

```yaml
  strategy:
    rollingUpdate:
      maxSurge: 1
      maxUnavailable: 1
    type: RollingUpdate
```

Specifies the **Strategy** used to replace old [[Pods]] by new ones. It can be **Recreate** or **Rolling Update**.

**Recreate** means all existing [[Pods]] are destroyed before new ones are created.
**Rolling Update** means [[Pods]] are destroyed and re-created one by one.

### Useful commands to know

`k create deploy test --image=httpd --replicas=3` create a **Deployment** using the httpd image, here we specified 3 replicas.

`k get deployment` list all the defined Deployments
`k edit deployment test` enter in edit mode for the deployment test.
`k descibe deployment test` describe the specified Deployment.
`k delete deployment test` delete the specified Deployment.

