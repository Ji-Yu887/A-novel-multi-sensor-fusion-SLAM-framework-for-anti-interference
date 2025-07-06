cmake_minimum_required(VERSION 3.5)
project(clahe_ros)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 强制指定 OpenCV 4.2 路径，避免找旧版本
set(OpenCV_DIR "/lib/aarch64-linux-gnu/cmake/opencv4")

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(cv_bridge REQUIRED)
find_package(image_transport REQUIRED)
find_package(OpenCV 4.2 REQUIRED COMPONENTS core imgproc imgcodecs)

include_directories(
  include
  ${OpenCV_INCLUDE_DIRS}
)

add_executable(clahe_ros_node
  src/clahe_ros_node.cpp
  src/clahe_ros.cpp
)

ament_target_dependencies(clahe_ros_node
  rclcpp
  sensor_msgs
  std_msgs
  cv_bridge
  image_transport
)

target_link_libraries(clahe_ros_node
  ${OpenCV_LIBS}
)

install(TARGETS clahe_ros_node
  ARCHIVE DESTINATION lib/${PROJECT_NAME}
  LIBRARY DESTINATION lib/${PROJECT_NAME}
  RUNTIME DESTINATION lib/${PROJECT_NAME}
)

install(DIRECTORY launch
  DESTINATION share/${PROJECT_NAME}/
)

install(PROGRAMS
  launch/clahe_ros.launch
  DESTINATION share/${PROJECT_NAME}/launch
)

ament_package()