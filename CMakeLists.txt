cmake_minimum_required(VERSION 3.16)
project(untitled)

set(CMAKE_CXX_STANDARD 20)

find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)
include_directories(${GLFW_INCLUDE_DIRS})

find_package(Vulkan REQUIRED)

add_executable(untitled main.cpp)
target_link_libraries(untitled ${GLFW_STATIC_LIBRARIES} Vulkan::Vulkan)
