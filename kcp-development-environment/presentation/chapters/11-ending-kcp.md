---
id: ending-kcp
type: terminal
---

# When this doesn't work

KCP will be useful if your team ships services and you need multi-tenancy up-front without the
hassle of dealing with namespaces, workload balancing and such.

And Postgres is just an example. Imagine who awesome of an experience this is for your service's users
to just create an instance and get something in return. Fully isolted, own RBAC, own.. everything.

Or, if you genuinely don't need this complex of an infrastructure.

Shameless plug: If you DO need this complex of an infrastructure, but you DON'T want to manage it yourself, [Kubermatic's Developer Platform](https://www.kubermatic.com/products/kubermatic-developer-platform/) built on KCP with a nice UI and management layer, has you covered.

It offers automated One-Click Service Instance Creation. A nice UI for a catalog, multi-tenancy fine-tuning, and a LOT more. 😊

**Thank you, Edinburgh.**

Adventure Voter:
![Adventure Voter](./adventure-voter.png)

KCP:
![KCP](kcp-qr-code.png)
