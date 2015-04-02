cmake_minimum_required(VERSION 2.8.3)
project(robotnik_arduimu)

find_package(catkin REQUIRED COMPONENTS 
    roscpp 
    tf
    nav_msgs 
    std_msgs
    std_srvs
    geometry_msgs 
    sensor_msgs 
    )

## System dependencies are found with CMake's conventions
# find_package(Boost REQUIRED COMPONENTS system)


catkin_package(
  INCLUDE_DIRS include

  CATKIN_DEPENDS 
    roscpp 
    tf
    nav_msgs 
    std_msgs
    geometry_msgs 
    sensor_msgs 

)

# include_directories(include)
include_directories(
  include
  ${Boost_INCLUDE_DIRS}
  ${catkin_INCLUDE_DIRS}
)

## Declare a cpp executable
add_executable(robotnik_arduimu src/robotnik_arduimu.cpp src/SerialDevice.cc)

## Specify libraries to link a library or executable target against
target_link_libraries(robotnik_arduimu ${catkin_LIBRARIES} )
