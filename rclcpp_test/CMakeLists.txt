cmake_minimum_required(VERSION 3.5)
project(ros_msg_rclcpp_test)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(ros_msg_test REQUIRED)

add_executable(pub_test pub_test.cpp)
ament_target_dependencies(pub_test rclcpp ros_msg_test)

install(TARGETS
  pub_test
  DESTINATION lib/${PROJECT_NAME}
)

ament_package() 
