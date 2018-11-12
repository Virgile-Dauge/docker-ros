FROM virgiletn/docker-ros:melodic-core
LABEL maintainer "virgile.dauge@telecomnancy.net"

#Installing all required dependencies according to the source cloned before
RUN apt-get -qq update \
    && apt-get install -y \
      apt-utils \
      ros-melodic-rviz \
      libgl1-mesa-glx  \
      libgl1-mesa-dri  \
    && rm -rf /var/lib/apt/lists/*

ADD https://raw.githubusercontent.com/virgileTN/docker-ros/master/rviz-intel/configs/vlp16.rviz /home/

#Launching rviz
CMD ["rosrun", "rviz", "rviz"]
