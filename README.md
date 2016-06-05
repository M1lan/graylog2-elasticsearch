# What is this?
Logging service for servers and Docker containers
using Graylog, ElasticSearch and
MongoDb. [https://hub.docker.com/r/graylog2/server/](https://hub.docker.com/r/graylog2/server/)

# Docker
## ~~Building~~
No need actually, because we're referencing to public images.

```
$ docker-compose build
elasticsearch uses an image, skipping
mongo uses an image, skipping
grayserver uses an image, skipping
```

## Running
Do this the first time
```
$ docker-compose up
docker-compose up
Pulling elasticsearch (elasticsearch:latest)...
latest: Pulling from library/elasticsearch...
```

Do this on the succeeding time
```
$ docker-compose start
Creating graylog-elasticsearch
Creating graylog-mongo
Creating graylog-grayserver
Attaching to graylog-elasticsearch, graylog-mongo, graylog-grayserver
```

## Kill/Stop the containers
```
$ docker-compose kill
Killing graylog-grayserver ... done
Killing graylog-mongo ... done
Killing graylog-elasticsearch ... done

$ docker compose stop
Stopping graylog-grayserver ... done
Stopping graylog-mongo ... done
Stopping graylog-elasticsearch ... done
```
## Cleanup the containers
```
$ docker-compose rm
Going to remove graylog-grayserver, graylog-mongo, graylog-elasticsearch
Are you sure? [yN] y
Removing graylog-grayserver ... done
Removing graylog-mongo ... done
Removing graylog-elasticsearch ... done
```

## Hard restart containers
```
$ docker-compose stop
$ docker-compose rm
$ docker-compose up
```

# Graylog
## Graylog Web Interface

Simply open [http://192.168.99.100:9000](http://192.168.99.100:9000) from your browser

Use the following login access

| username | password  |
|----------|-----------|
| admin    | password  |


## More configuration
Simply edit ```graylog.config``` and refer to Graylog server configuration. If anything is changed, do a hard restart on the containers.


# Todo
- Persist Graylog server data
- Persist MongoDb server data
- Persist ElasticSearch data

<sub><sup>** Persist by binding host directory to docker containers.</sup></sub>
