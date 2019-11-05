cmake_minimum_required(VERSION 2.8.3)
project(trajectory_smoothing_msg)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)


find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  message_generation
  geometry_msgs
)

add_message_files(
   FILES
   OpenPoseReceiverHuman.msg
   OpenPoseReceiverKeypoint.msg
   SmoothRWristCoordsWithRespectToBase.msg
)

generate_messages(
   DEPENDENCIES
   std_msgs
   geometry_msgs
)

catkin_package(CATKIN_DEPENDS message_runtime roscpp rospy std_msgs)

