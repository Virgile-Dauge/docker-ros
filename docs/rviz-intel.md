The rviz-intel image is designed to allow rviz visualisation tool easy use.
It require [Intel Hardware acceleration](https://github.com/virgileTN/docker-ros/wiki/Install#intel) to be installed on your computer.

You need to grant acces to your host machine xServer by launching the following :
```
xhost +
```
It grants acces to your xServer to any connected devices so be carefull and close it after use :
```
xhost -
```
## Docker cli
The simpliest way to launch it is the following :
```
docker run -it \
              --rm \
              --net host \
              --name rviz \
              --env ROS_HOSTNAME=$HOSTNAME \
              -ROS_MASTER_URI=http://$HOSTNAME:11311 \
              --volume=/tmp/.X11-unix:/tmp/.X11-unix \
              --env="DISPLAY" \
              virgiletn/docker-ros:melodic-rviz-intel \
              rosrun rviz rviz
```
Please see [Launch options page](https://github.com/virgileTN/docker-ros/wiki/launch-options) for more details on options.

## docker compose
See [docker-compose basics](https://github.com/virgileTN/docker-ros/wiki/docker-compose) if not already done.

Just add a new service in the service list :
```
rviz:
  image: virgiletn/docker-ros:melodic-rviz-intel
  container_name: rviz
  depends_on:
    - "master"
  environment:
      - "ROS_HOSTNAME=rviz"
      - "ROS_MASTER_URI=http://master:11311"
      - "DISPLAY"
  volumes:
      - /tmp/.X11-unix:/tmp/.X11-unix
  command: [rosrun, rviz, rviz]
```
You obviously need a ros master service called 'master' in our case.
