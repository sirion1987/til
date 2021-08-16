# How to create a new dokku app on DigitalOcean

Create a new app using DO marketplace. Copy the ip address and visit it on
the browser to finish the installation process.

Add a git remote for dokku: `git remote add dokku dokku@<ip_address>:<app_name>`

# Builbpack

## How to customize the buildpack url

```
$ dokku
    config:set <app_name> \
    BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-ruby.git
```

## How to customize the Heroku's stack

```
$ dokku \
    config:set <app_name> \
    STACK=[heroku-20|heroku-18|heroku-16|cedar-14]
```

## Creates postgres service

```
$ sudo dokku \
    plugin:install https://github.com/dokku/dokku-postgres.git postgres
```

```
$ dokku postgres:create <app_pg_service_name>
```

```
$ dokku postgres:link <app_pg_service_name> <app_name>
```

```
$ dokku postgres:import <app_pg_service_name> < latest.dump
```

## Configure virtual host

```
$ dokku domains:set <app_name> <url: e.g. www.example.com>
```

```
$ dokku domains:enable <app_name>
```

## Set environment variables

```
$ dokku config:set <app_name> <ENV_VAR>=<value>
```

Use `dokku config <app_name>` to see all env variables.

## Scalings app

See all available services in the procfile.

```
$ dokku ps:scale <app_name> web=1
```

## Add letsencrypt

```
$ sudo dokku plugin:install https://github.com/dokku/dokku-letsencrypt.git
```

```
$ dokku letsencrypt:enable <app_name>
```

```
$ dokku letsencrypt:auto-renew <app_name>
```

```
$ dokku letsencrypt:cron-job --add <app_name>
```

## Backups

```
$ dokku postgres:backup-auth <app_pg_service_name> <AWS_ACCESS_KEY_ID> <AWS_SECRET_ACCESS_KEY>
```

```
# Test a backup creation

$ dokku postgres:backup <app_pg_service_name> <bucket_name>
```

```
$ dokku postgres:backup-schedule <app_pg_service_name> <schedule> <bucket_name>
```

'schedule' is a crontab expression, eg. "0 3 * * *" for each day at 3am.

## Enable ports

```
$ sudo ufw allow 80
$ sudo ufw allow 443
```

- https://pawelurbanek.com/rails-heroku-dokku-migration
- https://pawelurbanek.com/optimize-dokku-deployment-speed
- https://stackoverflow.com/questions/21785901/dokku-add-domain-after-setup
