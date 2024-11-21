ROS1 support for Unbuntu 22.04 and after. Hence, we will use docker container to use the [visp_hand2eye_calibration](https://wiki.ros.org/visp_hand2eye_calibration) package.

To run a ROS1 Docker image, follow these steps:

1. Pull the ROS1 Docker Image
First, pull the official ROS1 Docker image from the OSRF (Open Source Robotics Foundation) repository:
```
docker pull osrf/ros:noetic-desktop-full
```
This command downloads the full ROS Noetic desktop image

2. Run the ROS1 Container
To start a ROS1 container, use the following command:
```
docker run -it osrf/ros:noetic-desktop-full
```
This command starts an interactive session with the running container.

3. Set Up the ROS Environment
Once inside the container, set up the ROS environment by sourcing the setup script:
```
source /opt/ros/noetic/setup.bash
```

4. Start ROS Core
To start the ROS master, run:
```
roscore
```
This will initiate the ROS core process.

5. Running Additional Nodes
To run additional ROS nodes or commands, you'll need to open new terminal windows and connect to the same container. Use the following steps:
Find the container name:
```
docker ps -l
```
Start a new bash session in the same container:
```
docker exec -it <container_name> bash
```
Set up the ROS environment in the new session:
```
source /opt/ros/noetic/setup.bash
```

The docker image won't have visp installed by default. You can install the ros-noetic-vision-visp package in a Docker container running ROS Noetic. 
Here's how you can do it:

1. Start with a ROS Noetic Docker image:
```
docker pull osrf/ros:noetic-desktop-full
```
2. Run the container in interactive mode:
```
docker run -it osrf/ros:noetic-desktop-full
```
3. Once inside the container, update the package lists:
```
apt-get update
```
4. Install the ros-noetic-vision-visp package:
```
apt-get install -y ros-noetic-vision-visp
```
This will install the ViSP-related packages for ROS Noetic inside your Docker container.
After installation, you can use the ViSP packages in your ROS projects within the container. Remember to source the ROS setup file if you haven't already:
```
source /opt/ros/noetic/setup.bash
```


