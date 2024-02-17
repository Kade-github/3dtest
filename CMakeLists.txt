cmake_minimum_required(VERSION 3.1...3.28)

project(
    3DTest
    VERSION 1.0
    LANGUAGES C CXX
)

include_directories(${CMAKE_SOURCE_DIR}/includes)
link_directories(${CMAKE_SOURCE_DIR}/library)

find_package(OpenGL REQUIRED)

find_path(
  GLFW_INCLUDE_DIR
  NAMES
  GLFW
  PATHS
  include)

find_library(
  GLFW_LIBRARY
  NAMES
  glfw glfw3 glfw3dll
  PATHS
  lib)

set(SOURCE_FILES main.cpp glad.c Shader.cpp Texture.cpp stbi.cpp "Camera.h")

add_executable(3DTest ${SOURCE_FILES})

target_link_libraries(3DTest glfw3)