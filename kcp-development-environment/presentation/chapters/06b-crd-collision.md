---
id: crd-collision
type: story
next: isolation-choice
---

# The Shared Cluster

Honestly? This mostly works. One cluster, a namespace per team, operators doing the provisioning, sensible quotas, everybody gets on with their day.

Right up until two teams need the same CRD at different versions.

```
$ kubectl apply -f operator-v2.yaml
The CustomResourceDefinition "widgets.acme.io" is invalid:
spec.versions: Invalid value: v1alpha1: must appear in spec.versions
```

Here is the thing nobody tells you on day one.

**Namespaces isolate objects. Namespaces do not isolate APIs.**

CRDs are cluster-scoped. So are ClusterRoles. So are admission webhooks, and the webhook one team installed last Tuesday is now intercepting every create in the cluster, including yours, and it is failing closed.

One developer upgrades an operator. Forty developers find out.

You did not hand out isolated API surfaces. You sat everybody at adjacent desks in a very quiet library, and gave one of them an air horn.
