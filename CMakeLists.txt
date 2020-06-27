cmake_minimum_required(VERSION 3.1)
cmake_policy(SET CMP0048 NEW)
cmake_policy(SET CMP0072 NEW)
cmake_policy(SET CMP0003 NEW)
project(opengl-testing VERSION 1.0)

find_package(OpenGL REQUIRED)

set(GLFW_BUILD_DOCS     OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS    OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(glfw)

add_executable(opengl-testing main.cpp glad.c)
target_link_libraries(opengl-testing glfw)
target_link_libraries(opengl-testing OpenGL::GL)
include_directories(PRIVATE include)