---
id: terraform-prs
type: story
next: the-real-problem
---

# `terraform plan`

Can be good if executed well. You create proper modules with guard rails. `modules/postgres` has encryption on, backups on, tags enforced, sensible defaults. A developer writes twelve lines and opens a PR.

Then, the problems start.

Where and how do you store the state file? A `plan` against the file takes eleven minutes.

No-one wants to wait that long so they start mixing PR content with more stuff
so they don't have to plan too often.

Review time is a thing unless you start _trusting_ people. **shudder**.

The infra repo has three hundred open pull requests now.

People start to be impatient and someone figures out how to run `apply` from their laptop against the infra
on 16:44 on a Wednesday.

```console
Plan: 0 to add, 0 to change, 47 to destroy.
```

Your Thursday is gone and your "queue" moved to GitHub (or GitLab (or BitBucket)).
