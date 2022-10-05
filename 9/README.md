# Introduction
Bacula Directory and Storage daemon version 9.0.6 server images based on CentOS 8

The main goal for this project is to upgrade Bacula Directory and Storage
Daemon version on the CentOS 7 server to have Bacula 9 version with keeping the original configuration.

## Installation and usage

Configuration files are expected to be in /etc/bacula. This image will not
create default database nor does it include default configuration files.
Tested with docker-ce 20.10.17 and docker-compose 1.18

Local build:
```
git clone https://github.com/martmaiste/bacula-docker.git
cd bacula-docker/9/
docker-compose build
docker-compose up -d
docker-compose logs --follow
```
