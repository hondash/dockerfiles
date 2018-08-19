# fluent-gce

A sample of docker containers(Rails + Nginx + CloudSQL + Fluentd) on Container-Optimized OS.


## Notes

Clone repository & Move files to home directory.

```
$ git clone https://github.com/hondash/dockerfiles.git
$ mv dockerfiles/fluent-gce/* ~/ && rm -rf dockerfiles
```

Add `.env` file to home directory

```
$ vi .env

RAILS_IMAGE=xxxxxxx
RAILS_APP_PATH=set rails base directory
CONFIG_PATH=set user home directory
INSTANCE_CONNECTION_NAME=xxxxx
```

Replace nginx config

```
$ sed -i -e 's/DOMAIN_NAME/YOUR_DOMAIN_NAME/g' nginx/conf.d/sample.conf
```

Run docker-compose

```
$ docker-compose up
```
