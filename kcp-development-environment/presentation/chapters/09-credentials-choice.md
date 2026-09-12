---
id: credentials-choice
type: decision
timer: 40
question: The database exists. Time to access it.
choices:
  - id: vault-direct
    label: Give everyone a Vault account
    description: It's the system of record.
    next: vault-for-everyone
  - id: ticket
    label: The user asks via a JIRA ticket.
    description: Platform has all the access.
    next: secret-by-ticket
  - id: eso
    label: Put the credentials in their workspace.
    description: Ask your cluster and ye shall receive.
    next: the-secret
---

# Where's The Password?

Let's explore a couple of options.
