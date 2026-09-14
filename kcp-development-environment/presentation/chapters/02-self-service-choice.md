---
id: self-service-choice
type: decision
timer: 60
question: Two hundred developers, six of you, everything is a ticket. What can we do?
choices:
  - id: terraform
    label: Publish Terraform modules, take PRs
    description: They create modules and you review them and apply standards
    next: terraform-prs
  - id: accounts
    label: A cloud account per team
    description: Real self-service. Who is legging the bill?
    next: account-each
  - id: helm
    label: A namespace and a Helm chart
    description: It's all in the chart. They just install it.
    next: helm-it-yourself
---

# Self-Service, Obviously

It's going to be a service that we provide. It's always some kind of service...
