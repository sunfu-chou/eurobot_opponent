cmake_minimum_required(VERSION 3.0.2)
project(eurobot_opponent)

set(CMAKE_CXX_FLAGS "-std=c++11 -fpermissive ${CMAKE_CXX_FLAGS} -Wfatal-errors\ ")

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  nlink_parser
  roscpp
  sensor_msgs
)

###########
## Build ##
###########

catkin_package(
)

include_directories(
  include 
  ${catkin_INCLUDE_DIRS}
)

add_executable(nlink_tagframe_converter src/nlink_tagframe_converter.cpp)
target_link_libraries(nlink_tagframe_converter ${catkin_LIBRARIES})
add_dependencies(nlink_tagframe_converter ${catkin_EXPORTED_TARGETS})
