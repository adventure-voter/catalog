---
id: credentials-choice
type: decision
timer: 40
question: The database exists. Alice needs the credentials. How does she get them?
choices:
  - id: vault-direct
    label: Give everyone a Vault account
    description: It's the system of record. Let her read her own path.
    next: vault-for-everyone
  - id: ticket
    label: She raises a ticket, we paste it in
    description: Platform team holds the keys. Controlled. Audited.
    next: secret-by-ticket
  - id: eso
    label: Put the credentials in her workspace
    description: She asks Kubernetes. Kubernetes answers.
    next: the-secret
---

# Where's The Password?

The database is real and it already exists. Terraform built it, or Crossplane, or a DBA called Dave. That part is solved.

The credentials live in Vault. Or AWS Secrets Manager. Or Azure Key Vault, because you acquired a company in 2023 and inherited their cloud along with their on-call rota.

Alice has access to none of them.

**Correctly.** She should not have production secret-store access because she needs a dev database.
