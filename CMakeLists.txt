cmake_minimum_required(VERSION 3.13)
project(COMP371_linux_skeleton)

set(CMAKE_CXX_STANDARD 11)
add_subdirectory(glfw)
include_directories(glfw/include)
find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)

add_executable(COMP371_linux_skeleton main.cpp)

FILE(COPY vertex.shader DESTINATION "${CMAKE_BINARY_DIR}")
FILE(COPY fragment.shader DESTINATION "${CMAKE_BINARY_DIR}")
FILE(COPY cube.obj DESTINATION "${CMAKE_BINARY_DIR}")

target_link_libraries(COMP371_linux_skeleton glfw ${OPENGL_glu_LIBRARY} ${GLFW_LIBRARIES} ${GLEW_LIBRARIES} ${OPENGL_LIBRARIES})

