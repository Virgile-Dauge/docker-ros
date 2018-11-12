The core image is designed to be lighweight as possible, and to be used as roscore.

The simpliest way to launch is the following (the network foo must be created first see [network](https://github.com/virgileTN/docker-ros/wiki/network) ):
```
docker run -it \
            --rm \
            --net simple-network \
            --name master \
            virgiletn/docker-ros:melodic-core
```
Please see [Launch options page](https://github.com/virgileTN/docker-ros/wiki/launch-options) for more details on options.

## docker compose
See [docker-compose basics](https://github.com/virgileTN/docker-ros/wiki/docker-compose) if not already done.

Just add a new service in the service list :
```
master:
  image: virgiletn/docker-ros:melodic-core
  container_name: master
```
