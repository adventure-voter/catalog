---
id: intro
type: story
next: self-service-choice
---

# Every Request Is A Ticket

You are the platform team. There are six of you. There are two hundred developers in the other teams.

They don't want a machine. They don't want a vm. No-one has asked for a machine in years.

They want a Postgres. A queue. A bucket. A credential that works. And they don't want a thousands
tools for these things.

Imagine taking a look at this queue:

```table
PLAT-4471  postgres for checkout-svc            Open   2d
PLAT-4472  S3 bucket + creds, staging           Open   2d
PLAT-4473  kafka topic (see PLAT-4470)          Open   3d
PLAT-4474  postgres for checkout-svc (dup?)     Open   1d
```

You are not a platform team. You are an API team with a two day latency and a human in the middle, and the human is you, and you have not written code since March.

**Scan the QR code. Pick badly. It's more fun.**
