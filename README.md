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
# 5-Launch Simulation World:

Three simulation environments are prepared for TurtleBot3. Please select one of these environments to launch Gazebo.

TurtleBot3 World
```
$ export TURTLEBOT3_MODEL=waffle
```
```
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
# 6-SLAM-Simulation:

Open a new terminal from Remote PC with Ctrl + Alt + T and run the SLAM node. Gmapping SLAM method is used by default.
Please use the proper keyword among burger , waffle , waffle_pi for the TURTLEBOT3_MODEL parameter.
```
$ export TURTLEBOT3_MODEL=waffle
```
```
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

![VirtualBox_Ross-s_03_08_2023_21_37_47](https://github.com/Layan-Alsaqer/SM23-AI02/assets/138806858/3b4fd723-40bf-45a5-8ecb-37ecb295cedb)

# 7-Run Teleoperation Node:
Open a new terminal from Remote PC with Ctrl + Alt + T and run the teleoperation node from the Remote PC.

Please use the proper keyword among burger , waffle , waffle_pi for the TURTLEBOT3_MODEL parameter.
```
$ export TURTLEBOT3_MODEL=waffle
```
```
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

![VirtualBox_Ross-s_03_08_2023_21_44_30](https://github.com/Layan-Alsaqer/SM23-AI02/assets/138806858/baa19523-e666-4cad-8091-f5ac17569294)

# 8-Save Map:

When the map is created successfully, open a new terminal from Remote PC with Ctrl + Alt + T and save the map.
```
$ rosrun map_server map_saver -f ~/map
```
![VirtualBox_Ross-s_03_08_2023_21_47_38](https://github.com/Layan-Alsaqer/SM23-AI02/assets/138806858/46f92aa9-65c7-4c62-8d76-3df41f660073)

