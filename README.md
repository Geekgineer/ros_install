# ROS Install 

Collection on bash scripts to automate ROS installation and setup
on workstation/PC/Laptops or Robots Computing board

> NOTE: intended for ROS Melodic on Ubuntu 18.04.xx but you can install any distro with it.

## ROS Install on Workstation/PC or Laptop

1. This will install ROS desktop version with gazebo and setup your catkin workspace

```sh
    $ ./install_ros_melodic_full_with_catkin_ws
```

2. This will install ROS desktop version with gazebo 

```sh
    $ ./install_ros_melodic_full
```

## ROS Install on a Robot Computer
This will install ROS base version on computer board such as Nvidia Jetson 

```sh
$ ./install_ros_melodic_minimum
```

```
NOTE: You can modify the above script to install 
ros-melodic-desktop-full/ros-melodic-desktop-full
or any ros distro to your machine
and also install your specific packages
```

## ROS Network Setup 
Scripts to setup ROS local network

### Configuration 1: ROS Master on the Robot computer

```
        Master                      Slave
+--------------------+      +-------------------+
|                    |      |                   |
|  Robot Computer    |      |  Workstation/PC   |
|                    |      |                   |
+--------------------+      +-------------------+ 

```

```sh
1. run this on the Robot Computer
    $ ./setup_ros_network_master 

# save the hostname printed in the terminal to use it as robothostname

2. run this on the Workstation/PC
    $ ./setup_ros_network_slave robothostname
```

## Configuration 1: ROS Master on the Workstation/PC

```

        Master                      Slave
+--------------------+      +-------------------+
|                    |      |                   |
|   Workstation/PC   |      |   Robot Computer  |
|                    |      |                   |
+--------------------+      +-------------------+ 

```

```sh
1. run this on the Workstation/PC
    $ ./setup_ros_network_master 

# save the hostname printed in the terminal to use it as localhostname

2. run this on the Robot Computer 
    $ ./setup_ros_network_slave localhostname
```

> robothostname: OS host name on the robot computing board

> localhostname: OS host name on personal computer/workstation 

> The master hostname could be the robot hostname or the workstation hostname

> The slave hostname could be the robot hostname or the workstation hostname
