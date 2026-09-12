---
id: gitops-works
type: story
next: isolation-choice
---

# This One Actually Works

GitOps with [Kro](https://kro.run/) or [Crossplane](https://www.crossplane.io/) and [Flux](https://docs.fluxcd.io/) or [Argo](https://argo-cd.readthedocs.io/en/stable/) is a deeply traversed path in this ecosystem.

A developer might just create a manifest like this:

```yaml
apiVersion: platform.acme.io/v1alpha1
kind: PostgresInstance
metadata:
  name: checkout
spec:
  size: small
  version: "16"
```

Open a PR, apply, reconcile, done.

Prevents manual meddling.

Auditable, `git revert` is something is busted.

This is a very good start and most companies stop here.

But wait. There is more!

![But wait, there is more!](./but-wait.jpg)
