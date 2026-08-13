# eduardocruz/marketplace

Plugin marketplace for [Claude Code](https://claude.com/claude-code).

```
/plugin marketplace add eduardocruz/marketplace
```

## Plugins

### throughline

Give your AI agent the context it is missing about your business — a goal
ladder, three guidelines drawn from real incidents, decisions with sources, and
a ten-check diagnosis of your repository. Runs entirely on your machine: no
account, no dependencies.

```
/plugin install throughline@eduardocruz-marketplace
```

Source and documentation: [eduardocruz/throughline](https://github.com/eduardocruz/throughline)

## Releasing

Each plugin lives in its own repository; this one only holds the catalogue, and
each entry pins an exact commit. After pushing a plugin release, bump its `sha`
here — nothing ships to users until that happens.

```
git ls-remote https://github.com/eduardocruz/throughline.git refs/heads/main
```

The `source` shape matters and is not interchangeable: `{"source": "github",
"repo": ...}` resolves to an SSH clone and fails for anyone without a GitHub key,
and `{"source": "git", ...}` is rejected by Claude Code 2.1.227 as an unsupported
source type. The form that works for an external repository is `{"source":
"url", "url": "...git", "sha": "..."}` — the same one the official marketplace
uses.

---

Who I am: [eduardocruz.com](https://eduardocruz.com) — fractional CTO, Laravel
and AI agents.
