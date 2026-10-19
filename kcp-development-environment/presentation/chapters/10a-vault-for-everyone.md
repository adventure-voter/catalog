---
id: vault-for-everyone
type: game-over
---

# Two Hundred Vault Accounts

Vault is an excellent software. That's not the problem.

You hand out accounts. And with them:

A new CLI. `vault kv get -field=password secret/data/db/alice`.

A new auth flow. OIDC, a browser tab, and a token that expires.

A new policy language, and a policy per developer, and a `path "secret/data/db/{{identity.entity.aliases...}}"` template that you will probably, most likely mistype or just plain
already forgot.

A new support queue. Though, to be fair, that will be a thing no matter how you solve it.

```console
$ vault kv get -field=password secret/data/db/alice
Error making API request.
Code: 403. Errors:
* 1 error occurred:
	* permission denied
```

Then, the company acquires another product and the secrets for that live in AWS Secrets Manager.

And so it begins:

```console
aws secretsmanager get-secret-value --secret-id
```

New CLI. New auth flow. New env. But still the same.

**GAME OVER**

_BUT! It's a good idea, the execution can be better!_
