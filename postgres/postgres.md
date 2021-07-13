# Dump

```
pg_dump \
  --verbose \
  --clean \
  --no-acl \
  --no-owner \
  -h localhost \
  -U postgres \
  -f dump.sql \
  -d <database_name>
```

# Restore a SQL dump

```
psql \
  -h localhost \
  -U postgres \
  -d <database_name> -f <source_file>
```

# Restore a dump

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
