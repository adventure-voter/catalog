---
id: crd-collision
type: story
next: isolation-choice
---

# The Shared Cluster

A shared cluster _mostly_ works. It has some downsides though.

Aside from the obvious shared resources...

CRD versioning is one that people don't think about often enough. When you need multiple versions of the same CRD, you'll get
problems (crds are cluster scoped): (so when someone adds a field to the same API....)

<!-- The old is being used, you can't remove it, and there is no migration path to the new one. -->

```console
$ kubectl apply -f operator-v2.yaml
The CustomResourceDefinition "widgets.acme.io" is invalid:
spec.versions: Invalid value: v1alpha1: must appear in spec.versions
```

Operator upgrades kill everyone at once.

The natural evolution of a shared cluster is... MOAR CLUSTERS!

![oprah](./oprah-cluster.jpg)
