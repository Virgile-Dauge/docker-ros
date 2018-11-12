## intro
Docker-compose allows to launch multiple services as containers. You will need to write a `docker-compose.yml`, then run a simple command :
```
docker-compose up
```

## docker-compose simple file example
A docker-compose file should at least have a version and a list of services. The version depends on docker-compose software version.
```
version: '3'
services:
  master:
    image: virgiletn/docker-ros:melodic-core
    container_name: master

  rviz:
    image: virgiletn/docker-ros:melodic-rviz-intel
    container_name: rviz
    depends_on:
      - "master"
    environment:
        - "ROS_HOSTNAME=master"
        - "ROS_MASTER_URI=http://master:11311"
        - "DISPLAY"
    volumes:
        - /tmp/.X11-unix:/tmp/.X11-unix
    command: [rosrun, rviz, rviz]
```

The `depends_on` ensure in our example that the ros master is in the list.

Here, a docker network is automatically created with the name of the `docker-compose.yml` directory.
