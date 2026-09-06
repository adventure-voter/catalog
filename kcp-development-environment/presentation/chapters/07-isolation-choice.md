---
id: isolation-choice
type: decision
timer: 40
question: Forty teams, each shipping APIs to the others. How do we isolate them?
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

The company grew. Forty teams now, and the thing you built worked so well that it changed what people build with it.

Teams stopped shipping *services* to each other and started shipping **APIs**. Your platform CRDs taught them the trick, and now every team has their own. One team's product is a `PaymentRoute` that three other teams depend on. Another's is a `FeatureGate` that eight more depend on.

Everyone needs their own API surface, their own CRD versions, their own RBAC.

Without their own cluster. And without the air horn.
