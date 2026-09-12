---
id: chatops-bot
type: story
next: isolation-choice
---

# `/provision postgres`

Coolness factor is nice!

```console
alice   /provision postgres --size small
bot     ✅  provisioning pg-alice-7f3 ... done (2m14s)
```

No new tools needed and the feedback is pretty good.

Then, the flood drains open:

*Where is my `-o yaml` output?*

*Ugh, someone requested this already at some point, I'm pretty sure... scroll, scroll, scroll.*

*I need to review it before it creates it.*

*Well, this broke. How do I even access the debug logs?*

Then, the bot dies. Dave leaves on a two week vacation. You built a glorified CLI that is arguably worse.
