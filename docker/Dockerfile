# 1. Start from the official ROS2 Humble desktop image (built on Ubuntu 22.04)
FROM osrf/ros:humble-desktop-full

# 2. Prevent interactive prompts during installation
ENV DEBIAN_FRONTEND=noninteractive

# 3. Install necessary tools and setup the Gazebo Fortress (Ignition) repository
RUN apt-get update && apt-get install -y \
    curl \
    gnupg \
    lsb-release \
    && curl https://osrfoundation.org --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg \
    && echo "deb [signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://osrfoundation.org $(lsb_release -cs) main" \
    > /etc/apt/sources.list.p/gazebo-stable.list

# 4. Install Gazebo Fortress and the ROS2 integration bridge
RUN apt-get update && apt-get install -y \
    ignition-fortress \
    ros-humble-ros-gz \
    && rm -rf /var/lib/apt/lists/*

# 5. Automatically source ROS2 and Gazebo setups when opening a terminal inside the container
RUN echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

# 6. Set the default working directory
WORKDIR /workspace
