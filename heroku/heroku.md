# Capture & download a backup

```
$ heroku pg:backups:capture
$ heroku pg:backups:download
```

# Show scheduled backups

```
heroku pg:backups:schedules
```

# Create a backup schedule

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
