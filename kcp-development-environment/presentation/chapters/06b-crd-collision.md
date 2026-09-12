---
id: crd-collision
type: story
next: isolation-choice
---

# The Shared Cluster

A shared cluster _mostly_ works. It has some downsides though, so lets dig into those.

CRD versioning is one obvious one. When you need multiple versions of the same CRD, you'll get
problems:

```console
$ kubectl apply -f operator-v2.yaml
The CustomResourceDefinition "widgets.acme.io" is invalid:
spec.versions: Invalid value: v1alpha1: must appear in spec.versions
```

Operator upgrades kill everyone at once.

The natural evolution of a shared cluster is... MOAR CLUSTERS!

![oprah](./oprah-cluster.jpg)
