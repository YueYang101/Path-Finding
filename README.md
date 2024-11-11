# Path-Finding

This project includes the steps to simulate open-source robot in gazebo and evaluate the performance of different path finding methods.


# Linux Setup on Windows
Install Ubuntu 22.04 on windows WSL.
Install Xlaunch to access the gui when using WSL.

# Setup Code
1.Installation of Gazebo Fortress
https://gazebosim.org/docs/fortress/install_ubuntu/a

<br>

2.Installation of ROS 2 Humble Hawksbill:
https://docs.ros.org/en/humble/Installation.html

<br>

3.ROS-Gazebo integration plug-in
```Bash
sudo apt update
sudo apt install ros-humble-gazebo-ros-pkgs
```
<br>

4.Install TurtleBot3 Packages
```Bash
sudo apt update
sudo apt install ros-humble-turtlebot3 ros-humble-turtlebot3-simulations
```
<br>

5.RViz2
```Bash
sudo apt update
sudo apt install ros-humble-rviz2
```
<br>

6.Automate Sourcing<br>
Open your .bashrc file:
```Bash
nano ~/.bashrc
```
<br>

Add the following lines at the end of the file:
```Bash
source /opt/ros/humble/setup.bash
source ~/turtlebot3_ws/install/setup.bash
export TURTLEBOT3_MODEL=burger  # or waffle, depending on your model
```
<br>

# Running codes
Launch gazebo with TurtleBot3
```Bash
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py use_sim_time:=true
```
<br>

Open RViz2 on another WSL terminal
```Bash
ros2 launch turtlebot3_bringup rviz2.launch.py use_sim_time:=true
```
<br>

