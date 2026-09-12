---
id: publish-the-api
type: story
next: credentials-choice
---

# Publish It Once

They have a control plane. It's empty.

The database has to come from _somewhere_. This is the last missing piece of this puzzle.

You define `once` what a `Postgres` database _IS_ for this company.

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

This is the catalog of this company.

The user takes one:

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

Now, there is an API for the user to play with.

**The user didn't install a CRD.**
**The user doesn't have to manage and operator.**
**Failures are surfaced through the status of the object.**
**Workspaces enforce multi-tenancy.**
**CRD versions are used when needed.**

The catalog is what the user is allowed to ask for. Just create the object.

```console
$ kubectl create -f postgres.yaml
postgresinstance.platform.acme.io/checkout created

$ kubectl get postgresinstance checkout
NAME       SIZE    VERSION   PHASE   AGE
checkout   small   16        Ready   96s
```

And then, there is the last question.
_Where is my password?_
