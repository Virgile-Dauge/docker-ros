The full-gui-intel image is designed to allow the use of all ros tools and librairies, including gui tools.

This image is quite heavy and should be used for debug/coding only.

It require [Intel Hardware acceleration](https://github.com/virgileTN/docker-ros/wiki/Install#intel) to be installed on your computer.

The simpliest way to launch it is the following :
```
docker run -it --rm \
                      --net simple-network \
                      --name full-gui-intel \
                      --env ROS_HOSTNAME=full-gui-intel \
                      --env ROS_MASTER_URI=http://master:11311 \
                      --volume=/tmp/.X11-unix:/tmp/.X11-unix \
                      --env="DISPLAY" \
                      --env QT_X11_NO_MITSHM=1 \
                      virgiletn/docker-ros:melodic-full-gui-intel
```
Please see [Launch options page](https://github.com/virgileTN/docker-ros/wiki/launch-options) for more details on options.
