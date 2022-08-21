# python-docker

This application consist of launching an MQTT client to subscribe to the 'python/mqtt/#' topic.

## Build image :

- $ cd python-docker
- $ docker build -t python-docker . # the '.' is to specify the path of the Dockerfile to be used.

## List images :

- $ docker images
- $ docker image ls

## Run image in foreground mode :

-$ docker run -p 8000:5000 python-docker

## Run image in detached mode :

- $ docker run -d -p 8000:5000 python-docker

## List containers :

- $ docker ps
- $ docker container ps

## Login container using bash :

- $ docker ps : to get container_name
- $ docker exec -it container_name /bin/bash

## Test application using the web browser :

- localhost:8000/ ==> Welcome to application
- localhost:8000/startApplication ==> Application started
- Launch the application in foreground mode and using another MQTT Client installed on your Linux PC try to publish a message and verify that it's received by the app ($ mosquitto_pub -d -h test.mosquitto.org -p 1883 -t "python/mqtt/fromTester" -m "hello form tester")

## Stop the application :

- Foreground mode : ctrl+c

- Detached mode : '$ docker ps' to get the container_name and '$ docker stop container_name' to stop the application
