---
id: ending-kcp
type: terminal
---

# The Interface Was The Product

A control plane per team, and a catalog of things they are allowed to have.

Databases, queues, buckets, credentials. You publish them as APIs. They bind them as APIs. Everything a developer needs arrives as an object in an API server they already knew how to talk to, and everything they are not allowed to have simply is not in their catalog.

That is the platform. The whole platform.

**Nobody had to learn anything.**

Not a portal. Not a CLI. Not a YAML dialect with a schema and a linter and a Confluence page nobody reads. Alice typed `kubectl get secret postgres`, it worked, and she went back to her actual job.

Every development environment you have ever hated, you hated because it made you learn *it* instead of letting you do your work.

---

## When this is the wrong answer

Be honest, because it often is.

**External Secrets on its own is worth doing today.** It needs no control planes, no workspaces and no strategy deck. One operator, a store your platform team owns, and developers stop pasting passwords into Slack. If you take one thing home, take that one.

The rest earns its complexity later. If you have four teams, one cluster and some quotas is fine. If Crossplane and Argo are holding up, leave them alone. If what your teams actually need is pods, use vcluster.

kcp starts paying at the point where **your teams ship APIs to each other**, where the API surface itself is the product and the multi-tenancy is real. Below that bar you are buying a control plane to solve a problem a `devcontainer.json` already solved last year.

And if you reach that bar, you do not have to operate any of this yourself. Kubermatic ships kcp as a product, [Kubermatic Developer Platform](https://www.kubermatic.com/products/kubermatic-developer-platform/), with the catalog and the onboarding already built. Buying the control plane is not the same mistake as building the portal.

Pick the boring answer until the boring answer stops working.

**Thank you, Edinburgh.**
