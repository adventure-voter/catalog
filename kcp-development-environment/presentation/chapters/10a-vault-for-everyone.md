---
id: vault-for-everyone
type: game-over
---

# Two Hundred Vault Accounts

Vault is excellent software. That is not what goes wrong here.

You hand out accounts. And with them:

A new CLI. `vault kv get -field=password secret/data/db/alice`.

A new auth flow. OIDC, a browser tab, a token that expires in eight hours, which means it expires at 16:55 on a Friday.

A new policy language, and a policy per developer, and a `path "secret/data/db/{{identity.entity.aliases...}}"` template that you will get wrong twice before you get it right.

A new support queue. Every `permission denied` is now yours.

```console
$ vault kv get -field=password secret/data/db/alice
Error making API request.
Code: 403. Errors:
* 1 error occurred:
	* permission denied
```

Then the second cloud arrives. The acquired product keeps its credentials in AWS Secrets Manager, so now it is `aws secretsmanager get-secret-value --secret-id`. Different CLI, different auth, different mental model, same developer.

And none of it helps at the only moment that matters, which is when her **application** needs the credential at runtime rather than her terminal. So she copies it into a `.env`. The `.env` reaches a commit. The commit is on a branch nobody ever deleted.

You handed two hundred people a dialect and made them learn it.

You have built the portal again. It is wearing a better hat.

**GAME OVER**

*Vault stays. It should. It just should not be the thing developers touch.*
