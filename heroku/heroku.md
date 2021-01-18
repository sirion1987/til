# Scheduled backups

```
heroku pg:backups:schedules
```

# Create scheduled backup

```
heroku pg:backups:schedule DATABASE_URL --at '02:00 Europe/Rome'
```

# Restore Database from remote url

```
$ heroku pg:backups -rstaging

=== Backups
ID    Created at      Status         Size      Database
────  ─────────────   ─────────────  ────────  ────────
a107  ...             ...            ...MB     DATABASE

$ DUMP_SIGNED_URL=$(heroku pg:backups:url <ID> -r<environment_source>)
$ heroku pg:backups:restore $DUMP_SIGNED_URL DATABASE_URL -r<environment_destination>
```
