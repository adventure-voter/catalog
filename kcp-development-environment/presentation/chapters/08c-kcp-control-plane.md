---
id: kcp-control-plane
type: story
next: publish-the-api
---

# A Control Plane Each

Not a cluster. A control plane.

```
$ kubectl create -f workspace.yaml
workspace.tenancy.kcp.io/alice created

$ kubectl get workspaces
NAME    TYPE        PHASE   URL
alice   universal   Ready   https://kcp.acme.internal/clusters/root:alice
```

An API server, RBAC, namespaces, service accounts, and their own CRDs which cannot collide with anybody else's. The compute stays where it always was, on real clusters, wired in behind the curtain.

You already know what that means and what it doesn't. Let's not spend your afternoon on it.

What matters is the bit you get for free: **every tool your developers own still works.** kubectl. Helm. Argo. k9s. The operators you already wrote. Onboarding is a kubeconfig.

Forty teams, forty API surfaces, nobody learned anything. Air horn confiscated.

And then you hand Alice her kubeconfig, and she looks at a completely empty control plane.

> *"Great. Where's my database?"*
