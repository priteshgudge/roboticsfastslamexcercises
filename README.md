# roboticsfastslamexcercises
Robotics Fast Slam Excercises

Excercises for Robotics Fast Slam Implementation using ROS and slam gmapping packages with the turtlebot robot model.

Installation of depthimage_to_laserscan github is required.



Running the project:

https://classroom.udacity.com/nanodegrees/nd209/parts/dad7b7cc-9cce-4be4-876e-30935216c8fa/modules/aec2781f-e368-4e1e-9aef-d46aeee55354/lessons/72a73c04-a318-425f-97eb-7c38cca1efb0/concepts/2201dcef-bee9-4693-8cb5-a1d41be181c2

First, clone the gmapping package, install its system dependencies, and build your catkin workspace

$ cd ~/catkin_ws/src
$ git clone https://github.com/ros-perception/slam_gmapping
$ rosdep install gmapping
$ cd..
$ catkin_make

Terminal 1

Launch the turtlebot in a Willow Garage environment

$ cd ~/catkin_ws
$ source devel/setup.bash
$ roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=worlds/willowgarage.world

Turtlebot should now appear in a Willow Garage environment.

Terminal 2

Launch the keyboard teleop node

$ cd ~/catkin_ws
$ source devel/setup.bash
$ roslaunch turtlebot_teleop keyboard_teleop.launch

Don’t move your robot yet!


Terminal 3

Run the slam_gmapping node

$ cd ~/catkin_ws
$ source devel/setup.bash
$ rosrun gmapping slam_gmapping

The node should start registering your first scan.

Terminal 4

Run rviz and subscribe to different published topics to visualize the map

$ rosrun rviz rviz

Edit the rviz configuration as follows:

    Change the Fixed Frame to base_link
    Change the Reference Frame to odom
    Add a RobotModel
    Add a camera and select the /camera/rgb/image_raw topic
    Add a map and select the /map topic

Now, map the environment by driving your robot using keyboard commands.

Terminal 5

Save a map of the environment and share it with your classmates

$ cd Desktop
$ rosrun map_server map_saver -f myMap
