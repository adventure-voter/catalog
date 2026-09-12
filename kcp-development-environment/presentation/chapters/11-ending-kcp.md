---
id: ending-kcp
type: terminal
---

# A control plane per team with a catalog

No portal, new custom CLI, no new flows to learn.

---

## When this doesn't work

Be honest, because it often is.

**External Secrets on its own is worth doing today.** It needs no control planes, no workspaces and no strategy deck. One operator, a store your platform team owns, and developers stop pasting passwords into Slack. If you take one thing home, take that one.

The rest earns its complexity later. If you have four teams, one cluster and some quotas is fine. If Crossplane and Argo are holding up, leave them alone. If what your teams actually need is pods, use vcluster.

kcp starts paying at the point where **your teams ship APIs to each other**, where the API surface itself is the product and the multi-tenancy is real. Below that bar you are buying a control plane to solve a problem a `devcontainer.json` already solved last year.

And if you reach that bar, you do not have to operate any of this yourself. Kubermatic ships kcp as a product, [Kubermatic Developer Platform](https://www.kubermatic.com/products/kubermatic-developer-platform/), with the catalog and the onboarding already built. Buying the control plane is not the same mistake as building the portal.

Pick the boring answer until the boring answer stops working.

**Thank you, Edinburgh.**
