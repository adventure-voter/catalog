---
id: gitops-works
type: story
next: isolation-choice
---

# This One Actually Works

Let's be honest about the good answer, because it exists and it is deeply unglamorous.

Your team defines, once, what a database *is* at this company. The instance, the subnet group, the parameter group, encryption, backups, the tags finance needs, the retention legal asked for. One composition. One place.

The developer writes this:

```yaml
apiVersion: platform.acme.io/v1alpha1
kind: PostgresInstance
metadata:
  name: checkout
spec:
  size: small
  version: "16"
```

They open a PR. Argo applies it. Crossplane reconciles it against the real cloud.

And if somebody deletes that database by hand at 02:00, it comes back, because the repository is the truth and the cloud is only a cache of it.

Real infrastructure. Reviewable, auditable, and rolled back with `git revert` like everything else they own.

This is genuinely good engineering. Plenty of excellent teams stop exactly here and are right to.

Hold on to one detail though, because it comes back at the end:

**It works because nobody had to learn anything.** They wrote some YAML and opened a pull request. They have been doing that since their first week.
