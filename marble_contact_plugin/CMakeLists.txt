cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
project(marble_contact_plugin)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(gazebo REQUIRED)

include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

add_library(MarbleContactPlugin SHARED MarbleContactPlugin.cc)
target_link_libraries(MarbleContactPlugin ${GAZEBO_libraries})
