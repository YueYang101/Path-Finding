# Path-Finding

This project includes the steps to simulate open-source robot in gazebo and evaluate the performance of different path finding methods.


# Linux Setup on Windows
Install Ubuntu 22.04 on windows WSL.
Install Xlaunch to access the gui when using WSL.

# Setup Code
## 1.Installation of Gazebo Fortress
https://gazebosim.org/docs/fortress/install_ubuntu/a

<br>

## 2.Installation of ROS 2 Humble Hawksbill:
https://docs.ros.org/en/humble/Installation.html

<br>

## 3.ROS-Gazebo integration plug-in
```Bash
sudo apt update
sudo apt install ros-humble-gazebo-ros-pkgs
```
<br>

## 4.Install TurtleBot3 Packages
```Bash
sudo apt update
sudo apt install ros-humble-turtlebot3 ros-humble-turtlebot3-simulations
```
<br>

## 5.RViz2
```Bash
sudo apt update
sudo apt install ros-humble-rviz2
```
<br>

## 6.Automate Sourcing<br>
Open your .bashrc file:
```Bash
nano ~/.bashrc
```
<br>

Add the following lines at the end of the file:
```Bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=waffle
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:/opt/ros/${ROS_DISTRO}/share/turtlebot3_gazebo/models
```
<br>

## 7.Navigation 2 Installation
```Bash
sudo apt update
sudo apt install -y ros-humble-navigation2 ros-humble-nav2-bringup

```
<br>

Create Workspace and Clone Nav2 Source
```Bash
mkdir -p ~/nav2_ws/src
cd ~/nav2_ws/src
git clone https://github.com/ros-planning/navigation2.git --branch humble
```
<br>

Install Dependencies and Build
```Bash
cd ~/nav2_ws
sudo apt update
sudo apt install -y python3-colcon-common-extensions
sudo apt install ros-humble-test-msgs
rosdep install -y -r -q --from-paths src --ignore-src --rosdistro humble
colcon build --parallel-workers 4
```
<br>

Source Workspace
```Bash
source ~/nav2_ws/install/setup.bash
```
<br>

# Running codes
## 1.Launch gazebo with TurtleBot3
```Bash
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py use_sim_time:=true
```
<br>

## 2.Open RViz2 on another WSL terminal
```Bash
ros2 launch turtlebot3_bringup rviz2.launch.py use_sim_time:=true
```
<br>

## 3. Running the demo with TB3
```Bash
ros2 launch nav2_bringup tb3_simulation_launch.py slam:=True headless:=False
```
<br>

## 4. run the package
```Bash
ros2 launch explore_lite explore.launch.py
```
<br>

# Raspberry pi 
```Bash
ssh yang@192.168.124.29
```
<br>