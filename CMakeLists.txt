cmake_minimum_required(VERSION 2.8.3)
project(opencv-for-catkin-sample)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES buoy
#  CATKIN_DEPENDS roscpp rospy std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(test src/test.cpp)
## Add folders to be run by python nosetests
# catkin_add_nosetests(test)
find_package(OpenCV)
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(test ${OpenCV_LIBRARIES})

