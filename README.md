# SM23-AI02
Use Turtlebot3 with SLAM approach to create and save a map
## SLAM Definition
The SLAM (Simultaneous Localization and Mapping) is a technique to draw a map by estimating current location in an arbitrary space. The SLAM is a well-known feature of TurtleBot from its predecessors. The video here shows you how accurately TurtleBot3 can draw a map with its compact and affordable platform.

All SLAM solutions include some kind of device or tool that allows a robot or other vehicle to observe and measure the environment around it.

This can be done by cameras, other types of image sensors, LiDAR laser scanner technology and even sonar. Essentially, any device that can be used to measure physical properties like location, distance or velocity can be included as part of a SLAM system. 

# 1-Install-ROS-on-Remote-PC:
Open the terminal with Ctrl + Alt + T and enter below commands one at a time.
In order to check the details of the easy installation script.

```
$ sudo apt update
```

```
$ sudo apt upgrade
```

```
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
```

```
$ chmod 755 ./install_ros_melodic.sh
```
```
$ bash ./install_ros_melodic.sh
```

# 2-Install-Dependent-ROS-Packages:
```
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```

# 3-Install-TurtleBot3-Packages:
Install TurtleBot3 via Debian Packages.
```
$ sudo apt install ros-melodic-dynamixel-sdk
```
```
$ sudo apt install ros-melodic-turtlebot3-msgs
```
```
$ sudo apt install ros-melodic-turtlebot3
```
# 4-Gazebo-Simulation:
Install Simulation Package:

The TurtleBot3 Simulation Package requires turtlebot3 and turtlebot3_msgs packages as prerequisite. Without these prerequisite packages, the Simulation cannot be launched.
Please follow the PC Setup instructions if you did not install required packages and dependent packages
```
$ cd ~/catkin_ws/src/
```
```
$ git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
```
```
$ cd ~/catkin_ws && catkin_make
```


