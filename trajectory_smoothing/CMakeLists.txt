cmake_minimum_required(VERSION 2.8.3)
project(trajectory_smoothing)

## Add support for C++11, supported in ROS Kinetic and newer
add_definitions(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  message_generation
  trajectory_smoothing_msg
  openpose_ros_msgs
  openpose_ros_receiver_msgs
  geometry_msgs 
)

find_package(Boost REQUIRED COMPONENTS system)

add_service_files(
   FILES
   Smooth.srv
)

generate_messages(
   DEPENDENCIES
   trajectory_smoothing_msg
   std_msgs
   geometry_msgs
)

catkin_package(
    CATKIN_DEPENDS message_runtime roscpp rospy std_msgs trajectory_smoothing_msg openpose_ros_msgs openpose_ros_receiver_msgs)

include_directories(
  include
  srv
  ${catkin_INCLUDE_DIRS}
)
