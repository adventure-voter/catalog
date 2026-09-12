---
id: kcp-control-plane
type: story
next: publish-the-api
---

# A Control Plane Each

_Not_ an entire cluster. Just the control plane!

```console
$ kubectl create -f workspace.yaml
workspace.tenancy.kcp.io/alice created

$ kubectl get workspaces
NAME    TYPE        PHASE   URL
alice   universal   Ready   https://kcp.acme.internal/clusters/root:alice
```

An API server with RBAC, namespaces, service accounts, and their own CRDs which can't collide with others.

Workloads stay on the original cluster.

What you get is **familiarity**.

And then you hand over the `kubeconfig` to a user and they go:

> _"Great. Where's my database?"_
