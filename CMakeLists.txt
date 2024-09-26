cmake_minimum_required(VERSION 3.5)
project(std_msgs_stamped)

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
  set(CMAKE_CXX_STANDARD_REQUIRED ON)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

set(msg_files
  "msg/BoolStamped.msg"
  "msg/ByteStamped.msg"
  "msg/ByteMultiArrayStamped.msg"
  "msg/CharStamped.msg"
  "msg/ColorRGBAStamped.msg"
  "msg/Float32Stamped.msg"
  "msg/Float32MultiArrayStamped.msg"
  "msg/Float64Stamped.msg"
  "msg/Float64MultiArrayStamped.msg"
  "msg/Int16Stamped.msg"
  "msg/Int16MultiArrayStamped.msg"
  "msg/Int32Stamped.msg"
  "msg/Int32MultiArrayStamped.msg"
  "msg/Int64Stamped.msg"
  "msg/Int64MultiArrayStamped.msg"
  "msg/Int8Stamped.msg"
  "msg/Int8MultiArrayStamped.msg"
  "msg/MultiArrayDimensionStamped.msg"
  "msg/MultiArrayLayoutStamped.msg"
  "msg/StringStamped.msg"
  "msg/UInt16Stamped.msg"
  "msg/UInt16MultiArrayStamped.msg"
  "msg/UInt32Stamped.msg"
  "msg/UInt32MultiArrayStamped.msg"
  "msg/UInt64Stamped.msg"
  "msg/UInt64MultiArrayStamped.msg"
  "msg/UInt8Stamped.msg"
  "msg/UInt8MultiArrayStamped.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  DEPENDENCIES builtin_interfaces
  ADD_LINTER_TESTS
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
