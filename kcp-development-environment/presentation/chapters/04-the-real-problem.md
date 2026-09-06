---
id: the-real-problem
type: story
next: interface-choice
---

# That Is Not Why It Failed

We could keep going. The wiki page of copy-paste snippets that three teams forked. The Backstage instance somebody installed during a hackathon which now nobody owns and nobody can turn off. Some vm bootstrapping that happens to launch *something somewhere*.

There are, of course, many other way. Even some proper ones. Proper scripts installed as tooling during onboarding.
Vault access for creds. Helm templating and in-house catalogs for applications and services to use and install.

But the real gap and problem on each instance was this:

**Every single one of them made a developer learn your infrastructure.**

HCL and a review queue. IAM and a billing console. A values file, and the operational burden.

The ask was not the infra in the beginning. The ask was a *service*. Or a **database**. Or an **access**.

Developers don't want to deal with where it came from. Don't want to deal with how it go there.
They want the thing and they want it now! And they **don't** want to learn a new tool to access it!

Let's go and build *that* instead.
