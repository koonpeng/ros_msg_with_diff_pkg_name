cmake_minimum_required(VERSION 3.5)

project(ros_msg_test)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)

set(msg_files
  "msg/Foo.msg"
)

rosidl_generate_interfaces(some_other_package_name
  ${msg_files}
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
