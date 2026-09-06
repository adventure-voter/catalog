---
id: chatops-bot
type: story
next: isolation-choice
---

# `/provision postgres`

One good afternoon of work, and the room will love you for a fortnight.

```
alice   /provision postgres --size small
bot     ✅  provisioning pg-alice-7f3 ... done (2m14s)
```

Zero new tools. They were in Slack regardless. Onboarding is a slash command.

Then the questions start arriving, and none of them have answers.

*"What did I actually get?"* There is no `-o yaml`. There was a message. The message has scrolled.

*"Who has what?"* Nobody knows. The state of your entire estate is now a distributed system made of chat history, and one of the nodes is a channel somebody archived.

*"Can I review this before it happens?"* No. No diff, no PR, no approval, no record that survives someone hovering over a message and clicking delete.

*"It broke, what changed?"* Slack search. On a Thursday. Good luck.

Then the bot stops responding mid-deploy and provisioning halts company-wide, and you discover it is a single Python process on a VM that Dave set up.

Dave left in June.

You wrote a CLI with no `--help`, no completion, no audit trail and no version control, and then you shipped it inside a chat client.

So you do the obvious thing, and move the request into git, where every other important decision at this company already lives.
