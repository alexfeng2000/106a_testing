# 106a Testing

To run the code, make sure you have the following packages:
http://wiki.ros.org/stereo_image_proc
http://wiki.ros.org/rtabmap_ros
http://wiki.ros.org/topic_tools/relay
http://wiki.ros.org/move_base
http://wiki.ros.org/move_base
http://wiki.ros.org/explore_lite

The following launch files:

To launch the gazebo simulation:
**export TURTLEBOT3_MODEL=waffle_stereo**
**roslaunch our_launch turtlebot3_world.launch world_name:=$(rospack find our_launch)/worlds/turtlebot3_world.world**

To launch image processing node:
**ROS_NAMESPACE=stereo rosrun stereo_image_proc stereo_image_proc**

To launch rtabmap_ros: 
**roslaunch our_launch stereo_mapping.launch**

To launch move_base:
**roslaunch our_launch move_base.launch**

To launch explore_lite:
**roslaunch our_launch explore.launch**

You may also have to use topic_tools in order to relay the map to explore_lite:
**rosrun topic_tools relay rtabmap/grid_map map**
in another terminal.
