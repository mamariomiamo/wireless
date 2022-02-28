cmake_minimum_required(VERSION 2.8.3)
project(wireless_watcher)

find_package(catkin REQUIRED)

find_package(catkin 
  COMPONENTS
  geometry_msgs
  mavros_msgs
  roscpp
  std_msgs
  common_msgs
  tf
  message_generation
)

catkin_package()

catkin_install_python(PROGRAMS
  nodes/watcher_node
  nodes/mavros_watcher
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
