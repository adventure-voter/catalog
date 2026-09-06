---
id: account-each
type: story
next: the-real-problem
---

# Here Are The Keys

Proper self-service. An account per team with a good starting point. A channel called `#cloud-help`, and all of your six people are in that channel.

This does work. For about three weeks.

Nobody uses tags, so nobody can say what anything costs, so nobody can turn anything off.

Somebody creates an RDS instance in `ap-southeast-2`, because the console remembered a region from a tutorial. It is still running. It has a public endpoint.

And every developer now needs IAM. Not "needs to use IAM". Needs to *understand* IAM, which is a whole different career!

Oh, and IRSA. Light afternoon reading anyone?

And then, of course, the numbers arrive:

```console
Account:  team-checkout
Period:   2026-07
Total:    £47,912.44
```

The alert went to a Slack channel that 99% of the people in it *muted*.

Your CFO now knows the phrase "NAT gateway data processing charges".
