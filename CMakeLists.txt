cmake_minimum_required(VERSION 3.12)
project(OpenGLTriangle)

set(CMAKE_CXX_STANDARD 17)

# GLAD
include_directories(include)

# GLFW
find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)
include_directories(${GLFW_INCLUDE_DIRS})

add_executable(OpenGLTriangle
    src/main.cpp
    src/glad.c
)

target_link_libraries(OpenGLTriangle ${GLFW_LIBRARIES} "-framework OpenGL")