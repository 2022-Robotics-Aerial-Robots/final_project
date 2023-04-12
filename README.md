# Final Project

Implementation Issue:
https://hackmd.io/@ncrl-10/SkwUc5QH9

The packages for 2022-AerialRobotics Final Project.

1. Rotor_simulator : UAV simulation using Geometric Controller

2. Husky : Ground Vehicle for assisting UAV challenge
    - Navigation
    - Localization
    - SLAM

3. Apriltag : For localization



# Requirements
* Ubuntu 20.04 ros-melodic
* gazebo greater than 9.0

```
sudo apt-get install ros-noetic-joy ros-noetic-octomap-ros ros-noetic-mavlink python-wstool python-catkin-tools protobuf-compiler libgoogle-glog-dev ros-noetic-control-toolbox
sudo apt-get install python-cvxopt
//or
sudo pip install cvxopt
```
# Additional package

## Rotor_simulator
This is a Gazebo simulation package for ros 20.04. The package is migrated from the [rotorS](https://github.com/ethz-asl/rotors_simulator).
```
sudo apt-get install ros-noetic-ompl
sudo apt-get install ros-noetic-mavros
sudo apt-get install ros-noetic-mavros-extras 
sudo apt-get install ros-noetic-mavros-msgs
sudo apt-get install ros-noetic-rm-msgs
sudo apt install ros-noetic-octomap-ros
sudo apt-get install libompl-dev
sudo apt install libgoogle-glog-dev 

cd /opt/ros/noetic/lib/mavros
sudo ./install_geographiclib_datasets.sh
```

## Husky
```
sudo apt-get install ros-noetic-husky-simulator
```
## Apriltag
```
sudo apt-get install ros-noetic-apriltag-ros
cd apriltag
cmake .
sudo make install
cd ..

# move apriltag installation folder to another folder to avoid error
mv apriltag/ ~/
```



# Running

## Setup
```
# if you don't have one, try to review ros architecture  and create one
cd ~/catkin_ws/src

git clone https://github.com/ethz-asl/mav_comm.git
git clone git@github.com:2022-Robotics-Aerial-Robots/Homework.git
mv /Homework/final_project final_project

# delete Homework file, you will need to enter the password
sudo rm -r /Homework

cd ~/catkin_ws

# it will take about 2-5 minutes for first time
catkin_make

# Remember if you cannot find launch file or node file, execute this command! 
source ~/catkin_ws/devel/setup.bash
```
## Spawn husky and quadcopter

```
roslaunch rotors_gazebo mav_hovering_example.launch 
```

![](https://i.imgur.com/NNoYdvO.png)

## Run position controller 
```
roslaunch rotors_gazebo controller_challenge.launch 
```
![](https://i.imgur.com/M255jPo.png)



# Challenge 1

## Apriltag tutorial
https://blog.csdn.net/wangmj_hdu/article/details/112668252
## Run Apriltag_detector
```
roslaunch apriltag_ros continuous_detection.launch
rostopic echo /tag_detections
```
![](https://i.imgur.com/8Ptwd8p.png)

