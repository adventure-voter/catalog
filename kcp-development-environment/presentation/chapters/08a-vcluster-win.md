---
id: vcluster-win
type: terminal
---

# You Were Right

`vcluster` (or some variation/product building on it). Every team gets a real API server, their own CRDs, their own RBAC, running as a pod on a host cluster.

And most importantly: **workloads still work.** `kubectl run nginx` runs nginx.

CRD collisions are gone. Everyone is an admin of their own cluster.

If you really _need_ a whole cluster, this, and others like this, are a viable solution.

If what your developers need is **a cluster that behaves like a cluster**, pods, deployments, services, etc, then this is probably enough.

Evolving this might make it better, but no need to touch something that works.

**THE END.**

_OR IS IT? Did you really solve the access issue to other clusters and APIs provided by other teams?_
