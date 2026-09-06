---
id: secret-by-ticket
type: game-over
---

# The Human API

Tight control. Only the platform team can read the secret store. Alice raises a ticket.

Two days later, somebody pastes the password into the ticket.

That ticket is now searchable by the entire company, forever, and it is indexed.

Then the interesting part. Your database rotates credentials every ninety days, a control you were genuinely proud of implementing.

Nothing downstream knows. At 03:00, twelve services fail authentication at the same instant, and the on-call engineer spends forty minutes proving the database is fine before anyone thinks to check the password.

Every rotation is now forty tickets. So rotation gets moved to a quarterly maintenance window. Then it gets moved again. Then someone sets the TTL to `0`.

Your ninety-day rotating credential is a four-year-old string in a Confluence page called **"DB creds (do not share)"**, which has been viewed one hundred and forty times.

You did not build a platform. You got yourself hired as a human API, and your rate limit is one ticket per two days.

**GAME OVER**
