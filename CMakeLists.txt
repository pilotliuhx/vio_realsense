cmake_minimum_required( VERSION 2.8 )
project( zjrobot_visual_odom )

set( CMAKE_BUILD_TYPE "Release" )
set( CMAKE_CXX_FLAGS "-std=c++11 -O3" )

#find_package( OpenCV 3.1 REQUIRED )
find_package( OpenCV REQUIRED ) # use this if in OpenCV2
find_package(realsense2 REQUIRED)
include_directories( 
    ${OpenCV_INCLUDE_DIRS}
)

add_executable( zjrobot_visual_odom realsense.cpp )
target_link_libraries( zjrobot_visual_odom ${OpenCV_LIBS} ${realsense2_LIBRARY})

