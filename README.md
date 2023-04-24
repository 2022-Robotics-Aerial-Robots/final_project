# Final Project

## Goal:
In this project, each team has to complete the following part:

1. (10%) Select 10 points and visualize them on Rviz.
2. (40%) Implement QP trajectory planning using points you selected in part 1, and visualize the trajectory on Rviz.
3. (10%) Run UAV's gazebo simulation and make it fly in the trajectory you planned with the following topic: "/${arg mav_name}/command/trajectory". Notice that the heading of it should be towards its velocity direction.
4. (40%) Construct a UAV formation team with one leader and two followers, the heading direction of them should be the same, and followers should remain behind the direction the leader is facing. (Coordinate transformation is needed)



Implementation Issue:
https://hackmd.io/@ncrl-10/SkwUc5QH9

The packages for 2022-AerialRobotics Final Project.

1. Rotor_simulator : UAV simulation using Geometric Controller


# Requirements
* Ubuntu 20.04 ros-noetic
* gazebo greater than 9.0

```
sudo apt-get install ros-noetic-joy ros-noetic-octomap-ros ros-noetic-mavlink  python3-wstool python3-catkin-tools protobuf-compiler libgoogle-glog-dev ros-noetic-control-toolbox
sudo apt-get install python3-cvxopt
```
## Additional package

### Rotor_simulator
This is a Gazebo simulation package for ros 20.04. The package is migrated from the [rotorS](https://github.com/ethz-asl/rotors_simulator).
```
sudo apt-get install ros-noetic-ompl
sudo apt-get install ros-noetic-mavros
sudo apt-get install ros-noetic-mavros-extras 
sudo apt-get install ros-noetic-mavros-msgs
sudo apt-get install ros-noetic-rm-msgs
sudo apt-get install libompl-dev
sudo apt install libgoogle-glog-dev 

cd /opt/ros/noetic/lib/mavros
sudo ./install_geographiclib_datasets.sh
```

## Running

### Setup

if you don't have one, try to review ros architecture  and create one
```
cd
mkdir -p final_project_ws/src
cd ~/final_project_ws/src
git clone https://github.com/ethz-asl/mav_comm.git
git clone https://github.com/2022-Robotics-Aerial-Robots/final_project.git
cd ~/final_project_ws
```

it will take about 2-5 minutes for first time
```
catkin_make
```
Remember if you cannot find launch file or node file, execute this command! 
```
source ~/final_project_ws/devel/setup.bash
```

Run the following command to make sure the gazebo simulation is installed correctly
```
roslaunch rotors_gazebo mav_hovering_example.launch
```
