# New project

```bash
$ mix phx.new <project_name> [--live]
```

# Install dependencies

```
$ mix archive.install hex <package_name>
```

* `phx_new`: Install Phoenix phx
* `ecto`: Install Ecto

# Generate a context for Ecto

```
$ mix phx.gen.context Accounts User     users  name:string ...
#                     plural   singular plural attributes
```
 
# Generate a migration

```
$ mix ecto.gen.migration <name>
```

# Run migrations

```
$ mix ecto.migrate
```
