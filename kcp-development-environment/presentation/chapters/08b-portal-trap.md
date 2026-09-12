---
id: portal-trap
type: game-over
---

# The Golden Path

You build a portal. It's beautiful. React, dark mode, progress bar, the works.

A CLI too, because hardcore devs live in the terminal: `acmectl env create`.

Then `acmectl env create --with-postgres`. Then `--with-postgres --version=16 --ha`. Then a YAML file, because the flags got out of hand. Then a schema for the YAML file, for verification and early typo warnings. Then a linter for the schema... and now you _HAVE_ to build a language server extension...

Then somebody asks, entirely reasonably, whether they can see the logs.

```console
$ acmectl env logs --follow
Error: unknown command "logs" for "acmectl env"
Did you mean this?
        list
```

This is a custom `kubectl`.

Next up: `-o yaml` `--watch` `explain`. You see where this is going...?

**GAME OVER**
