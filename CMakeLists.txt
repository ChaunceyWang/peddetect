cmake_minimum_required(VERSION 2.8.3)
project(peddetector)

set(CMAKE_BUILD_TYPE Debug)

include_directories(include)
find_package(OpenCV REQUIRED core imgproc highgui ml video calib3d objdetect)
include_directories(${OpenCV_INCLUDE_DIRS})

#set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
#add_definitions("-std=c++11")


file(GLOB folder_source src/*.cpp)
#source_group("Source Files" FILES ${folder_source})
add_executable(peddetector ${folder_source} )
target_link_libraries(peddetector ${OpenCV_LIBS})