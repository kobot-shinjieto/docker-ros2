# Base image with ROS 2 Humble
FROM osrf/ros:humble-desktop

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Update and install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    python3-pip \
    freeglut3-dev \
    ros-humble-moveit \
    ros-humble-moveit-ros \
    ros-humble-joint-state-broadcaster \
    ros-humble-joint-trajectory-controller \
    ros-humble-controller-manager \
    ros-humble-control-toolbox \
    ros-humble-position-controllers \
    ros-humble-moveit-resources \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip3 install --no-cache-dir \
    colcon-common-extensions \
    empy \
    pytest \
    numpy

# Create workspace
WORKDIR /root/ros2_ws

# Clone necessary repositories
# RUN git clone https://github.com/ros-planning/moveit2.git src/moveit2 \
#     && cd src/moveit2 && git checkout humble

# # Build workspace directly without rosdep
# RUN /bin/bash -c "source /opt/ros/humble/setup.bash && \
#     colcon build --cmake-args -DCMAKE_BUILD_TYPE=Release"

# # Source workspace
# RUN echo "source /root/ws_moveit2/install/setup.bash" >> ~/.bashrc
# RUN /bin/bash -c "source ~/.bashrc"

# Create workspace and set it as working directory
WORKDIR /root/ros2_ws

# Expose ports (if needed for debugging or communication)
EXPOSE 8888

# Set entrypoint
CMD ["bash"]