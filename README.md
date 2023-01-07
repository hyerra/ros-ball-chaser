# ros-ball-chaser
A robot that chases white-colored balls in an office enviornment created with Gazebo. This robot uses a camera sensor to detect the ball and drive in that direction.

This project is comprised of two ROS packages: `ball_chaser` and `robot`.

This was created as part of the [Udacity Robotics Software Engineer Nanodegree Program](https://www.udacity.com/course/robotics-software-engineer--nd209).

## Configuration

To correctly load the project, the `GAZEBO_MODEL_PATH` environment 
variable must be set:
```bash
$ export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:<path_to_robot_pkg>/models
```

## Running

This project uses [catkin](http://wiki.ros.org/catkin). Assuming you have catkin correctly setup, you can then run this project.

### Build Package

First, run the following to build the packages.
```bash
$ cd <path_to_catkin_ws>
$ catkin_make
```

### Start Project

In one terminal window, please run:
```bash
$ cd <path_to_catkin_ws>
$ source devel/setup.bash
$ roslaunch robot world.launch
```

In a second terminal window, please run:
```bash
$ cd <path_to_catkin_ws>
$ source devel/setup.bash
$ roslaunch ball_chaser ball_chaser.launch
```

You should then see the robot follow the white ball in Gazebo.

## RViz Setup

You can also visualize the scene using RViz. In order to do this, wait for RViz to show up by running the commands above. Then, on the left side of RViz under Displays, perform the following:
1. Select `odom` for Fixed Frame.
2. Click the Add button.
   1. Add `Robot Model` to display the robot in RViz.
   2. Add `Camera` and choose `/camera/rgb/image_raw` for the Image Topic.
   3. Add `Laser Scan` and select `/scan` for the Topic.

You should now be able to fully visualize the scene in RViz.
