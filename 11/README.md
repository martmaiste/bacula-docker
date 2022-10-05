# Introduction
Bacula Directory and Storage version 11 server images based on AlmaLinux 9

## Synopsis

The main goal of these Docker images of Bacula Directory and Storage daemons
is to have an easy upgrade path from Bacula version 9 to 11.

## Installation and usage

Configuration files are expected to be in /etc/bacula.

Local build:
```
git clone https://github.com/martmaiste/bacula-docker.git
cd bacula-docker/11/
docker-compose build
docker-compose up -d
docker-compose logs --follow
```

Upgrade PostgreSQL database running on the host from Bacula version 9 to 11:
```
docker run --network host -ti bacula-dir:11 bash
export PGHOST=127.0.0.1
export PGUSER=bacula
export PGNAME=bacula
/usr/libexec/bacula/update_postgresql_tables
```