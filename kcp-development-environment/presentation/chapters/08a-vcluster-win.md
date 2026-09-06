---
id: vcluster-win
type: terminal
---

# You Were Right

vcluster. Every team gets a real API server, their own CRDs, their own RBAC, running as a pod on a host cluster your team already knows how to operate.

And critically: **workloads still work.** `kubectl run nginx` runs nginx. There is a kubelet down there somewhere. Someone else's kubelet, but a real one.

CRD collisions: gone. Cluster-admin without handing out a cluster: yes. Cost: a fraction of a cluster each.

If what your developers need is **a cluster that behaves like a cluster**, pods, deployments, services, the whole familiar surface, then this is the correct answer, and reaching for something more exotic would be architecture astronautics.

You solved the problem you actually had. That is the entire job.

**THE END.** And a good one.

*There is one more door, though. Behind it, the hard part was never the compute. It was the credentials.*
