---
id: helm-it-yourself
type: story
next: the-real-problem
---

# `helm install postgres`

The cheapest answer, and it kinda works.

```console
$ helm install postgres bitnami/postgresql
NAME: postgres
STATUS: deployed
```

Fast. Reliable. Easy.

**Week three.** A node drains during a routine upgrade. The pod moves. The data does not, because the default is `emptyDir` and people don't read defaults properly.

**Week five.** Someone needs a restore. There are no backups. There was never anything taking backups. No snapshot, no WAL archive, no cron, no plan.

**Week eight.** Twelve of these exist.

And all twelve are **important**, because _some customer is running against this instance in dev_ (literally a phrase uttered MORE THAN ONCE that **I** heard).

Now you shifted the operational costs and burdens over to the developers and they took it gleefully.
