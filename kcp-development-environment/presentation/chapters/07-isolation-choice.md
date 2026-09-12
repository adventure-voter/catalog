---
id: isolation-choice
type: decision
timer: 40
question: Too many teams, too many choices.
choices:
  - id: vcluster
    label: Virtual clusters on a shared host
    description: A real API server each. Workloads included.
    next: vcluster-win
  - id: portal
    label: Build an internal portal and a CLI
    description: One golden path. We own the whole experience.
    next: portal-trap
  - id: kcp
    label: A control plane each, not a cluster
    description: Workspaces. Kubernetes-shaped, minus the compute.
    next: kcp-control-plane
---

# Two Years Later

The company grows and now there are forty teams and they all learned to ship _services_ and **APIs** to each other
rather than tars or gzips. You trained them well.

One team's product is a `PaymentRoute` that three other teams depend on. Another's is a `FeatureGate` that eight more depend on.

Everything needs its own CRD, RBAC, API surface, service accounts, user handling...
