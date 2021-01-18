# Restore dump

```
pg_restore \
  --verbose --clean --no-acl --no-owner \
  -h localhost \
  -U postgres \
  -d <database_name> \
  latest.dump
```
# Materialied View & View

poche query e tante insert => view
tante query e poche insert => materialized_view

# Psql

```
psql \
  -h localhost \
  -U postgres \
  -d <database_name>
```
