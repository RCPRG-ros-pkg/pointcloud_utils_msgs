cmake_minimum_required(VERSION 2.8.6)

project(pointcloud_utils_msgs)

find_package(catkin REQUIRED
  COMPONENTS roscpp rospy std_msgs geometry_msgs message_generation actionlib_msgs)

#add_action_files(
#  DIRECTORY action
#  FILES
#  CartesianTrajectory.action
#  CartesianImpedance.action
#)

#add_message_files(FILES
#  CartesianImpedance.msg
#  CartesianTrajectory.msg
#  )
  
add_service_files(
  DIRECTORY srv
  FILES
  FindPlanes.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
  actionlib_msgs
  )

catkin_package(
  CATKIN_DEPENDS std_msgs geometry_msgs message_runtime)
