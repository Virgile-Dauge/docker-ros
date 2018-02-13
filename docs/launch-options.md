## Docker run Options

```
-it  
```
allows visuals returns in console.
```
--rm  
```
Automatically remove the container when it exits
```
--name coucou  
```
simply name the container (in this case it will be called coucou), it's always a good idea to name containers
```
--net foo
```
give access to the foo network
See [network](https://github.com/virgileTN/docker-ros/wiki/network) for more details.

## specific Ros options
```
--env ROS_HOSTNAME=node-example-name \
```
Is used for setting the current container node name
```
--env ROS_MASTER_URI=http://master:11311 \
```
Is used for finding rosmaster

## specific Graphic acceleration options

```
--volume=/tmp/.X11-unix:/tmp/.X11-unix \
```
Is used for sharing graphical drivers
```
--env="DISPLAY" \
```
Is used to allow use of host machine screen
