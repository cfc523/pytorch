# Basic CMake setup
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
project(custom_ops)

find_package(Torch REQUIRED)

add_library(custom_ops SHARED op.cpp)
target_link_libraries(custom_ops ${TORCH_LIBRARIES})

add_executable(test_custom_ops test_custom_ops.cpp)
target_link_libraries(test_custom_ops custom_ops)
