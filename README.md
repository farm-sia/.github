# FARM
#### Fully Autonomous Room Mapper

## Description

The robot can navigate autonomously through a room, just with the help of a map it created itself and is getting updated in realtime (zero knowledge of environment required).

## Technology

We are using a LiDAR Sensor (RPLIDAR-A1) to get a 2D View of the environment.
The output of the Sensor is fed to an SLAM algorithm (Simultaneous Localization and Mapping, we are using Google Cartographer running under the ROS, Robot Operating System). The ROS and SLAM Algorithm are run completely on the robot using an RaspberryPi 4 8GB, so no remote device is needed, but it is optional to monitor the activity of the robot.

The SLAM algorithm does also get data from a MPU and from the roatary encoders of the motors to finetune the outcome.

The map gets transferred to a remote device (in our case a laptop) over a websocket connection, which required the remote device and robot to be in the same WIFI, which we solved by connecting the robot to a hotspot hostet by the laptop.

## Demo

A demo video is available [here](https://farm.bgfxc4.de).
