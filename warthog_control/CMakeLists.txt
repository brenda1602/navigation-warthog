cmake_minimum_required(VERSION 3.0.2)
project(warthog_control)

find_package(catkin REQUIRED COMPONENTS roslaunch geometry_msgs)

catkin_package(  INCLUDE_DIRS
CATKIN_DEPENDS geometry_msgs joy rospy
DEPENDS)

roslaunch_add_file_check(launch/control.launch)
roslaunch_add_file_check(launch/teleop.launch)
roslaunch_add_file_check(launch/keyboard_teleop.launch)

install(PROGRAMS
  scripts/warthog_teleop_key
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY config launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)