# Direnv

- https://direnv.net/

# How to load the local environment

```bash
# .envrc

export VAR=

[[ -f .envrc.private ]] && source_env .envrc.private
```

```bash
# .envrc.private

export VAR=XXX-XXX-XXX
```
