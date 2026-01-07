cmake_minimum_required(VERSION 3.8)
project(system_msgs)

# C++警告オプション
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# 依存関係
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)

# msgファイルをPython用に生成
rosidl_generate_interfaces(${PROJECT_NAME}	
  "msg/RmEvent.msg"
  "msg/RmNotioncmd.msg"
  "msg/RmStatus.msg"
  "msg/Response.msg"	
  DEPENDENCIES builtin_interfaces std_msgs
)

# テスト/リンター
if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  set(ament_cmake_copyright_FOUND TRUE)
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

# パッケージとしてROS2に認識させる
ament_export_dependencies(rosidl_default_runtime)

ament_package()
