---
id: interface-choice
type: decision
timer: 40
question: They should ask for a database, not a VPC. So what do they actually talk to?
choices:
  - id: chatops
    label: A Slack bot
    description: /provision postgres. They're in Slack anyway. Zero new tools.
    next: chatops-bot
  - id: operators
    label: Operators and CRDs on a shared cluster
    description: kubectl apply. Real controllers, real reconciliation.
    next: crd-collision
  - id: gitops
    label: Crossplane compositions, applied by Argo
    description: They commit YAML. The cluster does the rest.
    next: gitops-works
---

# Ask For A Database

Not a module. Not an account. Not a VPC.

```console
"Postgres 16, small, eu-west-1, and I need the password."
```

That is the only thing and everything that leads to this, is none of their business.
