cmake_minimum_required(VERSION 3.8)
project(vision)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()


find_package(ament_cmake_python REQUIRED)
find_package(rclpy REQUIRED)
find_package(sensor_msgs REQUIRED)


ament_python_install_package(${PROJECT_NAME})

install(PROGRAMS
  scripts/net_finder.py
  scripts/camera_debug.py
  scripts/camera.py
  scripts/net_finder_debug.py
  scripts/camera_spoofer.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
