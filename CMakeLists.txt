cmake_minimum_required(VERSION 3.1...3.28)

project(
    3DTest
    VERSION 1.0
    LANGUAGES C CXX
)

find_package(OpenGL REQUIRED)

find_package(glfw3 REQUIRED)

set(SOURCE_FILES main.cpp glad.c Shader.cpp)

add_executable(3DTest ${SOURCE_FILES})

target_link_libraries(3DTest glfw)