
<p align="middle">
<img src="https://github.com/JorgeLZ13/Warehouse_Gazebo/blob/main/gazebo-simulations.png"  height="352" width="555"/>
</p>

<h1 align="center">L-Bot: a Warehouse Robot Simulation</h1>


## Description
Inspired by robots like the Kiva robot, the L-Bot is a robot for distribution centers simulated through the gazebo. Using the control implemented in the robot, we can move around the warehouse,go under the shelves and activate the lift tray system,adapt the speed of the robot and perform the monitoring of several sensors. In order to bring simulation as close as possible to reality, we have implemented the laser sensor with an angle opening of 135° making it possible to calculate the distance to avoid collisions with the shelves,walls and even other robots, a camera at the bottom of the robot for reading qrcodes used to locate the robot, sensors such as wheel odometry and IMU are also present.

>Status: 🚧 In progress 🚧


## Application Demo

<img src="https://github.com/JorgeLZ13/Warehouse_Gazebo/blob/main/laser_bot.png"  height="238" width="392"/>
<!--<img src="https://github.com/JorgeLZ13/Warehouse_Gazebo/blob/main/warehouse_gazebo.png"  height="366" width="651"/> -->

![warehouse_simulation](https://github.com/JorgeLZ13/Warehouse_Gazebo/blob/main/warehouse_gif.gif)

Click on the image below to watch a demonstration of the simulation: <br >

[![Warehouse Gazebo Simulation](http://img.youtube.com/vi/3MY5E4lOR98/0.jpg)](http://www.youtube.com/watch?v=3MY5E4lOR98 "Warehouse Gazebo Simulation")



Contents
=================
<!--ts-->
   * [Description](#Description)
   * [Application Demo](#Application-Demo)
   * [Requirements](#Requirements)
   * [Installation](#Installation)
   * [Running the Simulation](#Running-the-Simulation)
      * [How to run the simulation environment](#How-to-run-the-simulation-environment)
      * [How to run the robot control](#How-to-run-the-robot-control)
      * [How to run the Rviz](#How-to-run-the-Rviz)
   * [Autor](#Autor)
<!--te-->

## Requirements
* Ubuntu 20.04
* <a href="http://wiki.ros.org/noetic/Installation/Ubuntu"> ROS Noetic</a>
* <a href="http://gazebosim.org/tutorials?tut=install_ubuntu"> Gazebo</a>
* <a href="http://gazebosim.org/tutorials?tut=ros_installing&cat=connect_ros"> Gazebo ROS Packages</a>
* <a href="http://wiki.ros.org/rviz/UserGuide"> Rviz</a>
* <a href="https://docs.python-guide.org/starting/install3/linux/"> Python 3.8</a>
* <a href="http://wiki.ros.org/ros_control"> ROS Control</a>

## Installation
In your workspace inside the <code>src</code> folder, place the <code>robot_description</code> and <code>robot_control</code> packages
then do the following command to install the packages:

<pre>
catkin_make
</pre>


## Running the Simulation

### How to run the simulation environment
You can now use the following command to start the environment (use these commands within your workspace):

<pre>
source ./devel/setup.bash<br />
roslaunch robot_description spawn.launch
</pre>

If all goes well you will see L-Bot inside the middle of the warehouse.

### How to run the robot control

If you want to move the robot through the warehouse use the following commands:
<pre>
source ./devel/setup.bash<br />
roslaunch robot_control control.launch
</pre>

To move the tray open another terminal and use the command below with <code>"data: 1"</code> to go up and <code>"data: 0"</code> to go down:

<pre>
rostopic pub -1 /my_robot/joint1_position_controller/command std_msgs/Float64 "data: 0"
</pre>

### How to run the Rviz
To use sensors like <code>camera</code> and <code>laser</code> we created a shortcut through Rviz:

<pre>
source ./devel/setup.bash <br />
roslaunch robot_description rviz.launch
</pre>

## Autor
