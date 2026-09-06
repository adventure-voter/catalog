---
id: publish-the-api
type: story
next: credentials-choice
---

# Publish It Once

Alice has a control plane. It is empty.

Somebody still has to put a database in it, and this is the part where every previous answer on this board fell over.

Not this time. Your team defines what a Postgres is at this company, exactly once, in a workspace Alice will never visit.

```yaml
apiVersion: apis.kcp.io/v1alpha1
kind: APIExport
metadata:
  name: platform.acme.io
spec:
  latestResourceSchemas:
    - v250901.postgresinstances.platform.acme.io
    - v250901.queues.platform.acme.io
    - v250901.buckets.platform.acme.io
```

That is the catalog. Three lines, three products.

Alice takes one:

```yaml
apiVersion: apis.kcp.io/v1alpha1
kind: APIBinding
metadata:
  name: platform
spec:
  reference:
    export:
      path: root:platform
      name: platform.acme.io
```

```console
$ kubectl api-resources | grep platform.acme.io
postgresinstances   platform.acme.io/v1alpha1   true   PostgresInstance
queues              platform.acme.io/v1alpha1   true   Queue
buckets             platform.acme.io/v1alpha1   true   Bucket
```

The API is in her control plane. Now look at what nobody did.

**Nobody installed a CRD.** Not Alice, not you, not in her workspace. There is no CRD to collide with, because the schema is not hers and never was. That air horn from earlier does not exist here.

**Nobody deployed a controller.** One reconciler runs, in your workspace, against one virtual endpoint that serves every `PostgresInstance` in the company at once. Forty tenants. One deployment. One thing to page you.

**Nobody wrote RBAC for the other thirty-nine.** Alice cannot see them. There is no list call that would return them. Multi-tenancy is not a policy you enforced, it is the shape of the thing.

And when you ship `v1beta1` next quarter, you publish it and teams bind it when they are ready. Nobody's Tuesday is ruined by your Tuesday.

This is the Crossplane composition from earlier, kept exactly as it was, and handed out as an **API** instead of a shared cluster.

The catalog is the platform. What is in Alice's catalog is what Alice is allowed to have, and there is no portal in which to enforce that, because there is no portal.

So she asks for one.

```console
$ kubectl create -f postgres.yaml
postgresinstance.platform.acme.io/checkout created

$ kubectl get postgresinstance checkout
NAME       SIZE    VERSION   PHASE   AGE
checkout   small   16        Ready   96s
```

Real database. Real cloud. `kubectl`.

And then Alice asks the only question left.

> *"Where's the password?"*
