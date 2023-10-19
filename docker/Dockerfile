FROM ros:humble

WORKDIR /ros2_ws/src

RUN apt update \
    && apt install -y \
    ros-humble-octomap \
    ros-humble-octomap-server

RUN git clone --branch fix/build https://github.com/macnack/octomap_server2.git \
    && cd octomap_server2 \
    && vcs import . < deps.repos

WORKDIR /ros2_ws

RUN . /opt/ros/humble/setup.sh \
    && colcon build

CMD [ "bash" ]