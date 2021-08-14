# Postgres

```
#!/usr/bin/env bash

PG_VERSION=${1:-12}
VOLUME=${2:-pg$PG_VERSION}

mkdir -p /tmp/docker-pg
chmod 0777 /tmp/docker-pg

docker \
  run \
  --detach \
  --publish 5432:5432 \
  --rm \
  --volume /tmp/docker-pg:/tmp \
  --volume $VOLUME:/var/lib/postgresql/data \
  --env POSTGRES_HOST_AUTH_METHOD=trust \
  postgres:$PG_VERSION
```

## psql

`psql -h localhost -U postgres -d <DATABASE_NAME>`

# MariaDB

```
#!/usr/bin/env bash

mkdir -p /tmp/docker-mariadb
chmod 0777 /tmp/docker-mariadb

docker \
  run \
  --publish 3306:3306 \
  --rm \
  --volume /tmp/docker-mariadb:/tmp \
  --volume mariadb:/var/lib/mysql \
  --env MARIADB_ROOT_PASSWORD=password \
  --env MYSQL_DATABASE=wordpress \
  mariadb
```

## Import db

```
mysql \
  -u root \
  -h <ip_address> \
  -P 3306 \
  -D <database_name>\
< dump.sql
```

# FakeS3

```
#!/usr/bin/env bash

docker \
  run \
  --publish 4569:4569 \
  kuracloud/fake-s3
```

# Redis

```
REDIS_VERSION=${1:-latest}

docker \
  run
  --detach
  --publish 6379:6379
  redis:$REDIS_VERSION
```

# How to get the IP address

```
$ docker ps -a
$ docker inspect <CONTAINER_ID> | grep IPAddress
```

# Notes

* [Don’t install Postgres. Docker pull Postgres](https://hackernoon.com/dont-install-postgres-docker-pull-postgres-bee20e200198)
* [Connect From Your Local Machine to a PostgreSQL Database in Docker](https://medium.com/better-programming/connect-from-local-machine-to-postgresql-docker-container-f785f00461a7)
