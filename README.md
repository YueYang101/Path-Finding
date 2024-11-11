# Path-Finding

This project includes the steps to simulate open-source robot in gazebo and evaluate the performance of different path finding methods.


# Linux Setup on Windows
Install Ubuntu 22.04 on windows WSL.
Install Xlaunch to access the gui when using WSL.

# Setup Code
1.Installation of Gazebo Fortress
https://gazebosim.org/docs/fortress/install_ubuntu/a

2.Installation of ROS 2 Humble Hawksbill:
https://docs.ros.org/en/humble/Installation.html

3.ROS-Gazebo integration plug-in
```Bash
sudo apt update
sudo apt install ros-humble-gazebo-ros-pkgs
```

4.Install TurtleBot3 Packages
```Bash
sudo apt update
sudo apt install ros-humble-turtlebot3 ros-humble-turtlebot3-simulations
```

5.RViz2
```Bash
sudo apt update
sudo apt install ros-humble-rviz2
```

6.Automate Sourcing  
Open your .bashrc file:
```Bash
nano ~/.bashrc
```
Add the following lines at the end of the file:
```Bash
source /opt/ros/humble/setup.bash
source ~/turtlebot3_ws/install/setup.bash
export TURTLEBOT3_MODEL=burger  # or waffle, depending on your model
```