---
id: portal-trap
type: game-over
---

# The Golden Path

You build the portal. It is genuinely lovely. React, dark mode, a wizard with a progress bar.

Then a CLI, because developers hate clicking: `acmectl env create`.

Then `acmectl env create --with-postgres`. Then `--with-postgres --version=16 --ha`. Then a YAML file, because the flags got out of hand. Then a schema for the YAML file. Then a linter for the schema.

Then somebody asks, entirely reasonably, whether they can see the logs.

```
$ acmectl env logs --follow
Error: unknown command "logs" for "acmectl env"
Did you mean this?
        list
```

You have written a worse kubectl.

No `-o yaml`. No `--watch`. No `explain`. No shell completion worth the name. It does not work with k9s, Argo, Flux, Helm, Terraform, or a single one of the thousand tools your developers already had open.

You did not build a platform. You built a **dialect**, and then you made two hundred people learn it.

**GAME OVER**
