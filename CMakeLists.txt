cmake_minimum_required(VERSION 3.19)
project(OpenGl2)

set(CMAKE_CXX_STANDARD 17)

include_directories("include/")
include_directories("Dependencies/glfw-3.3.4/include")
include_directories("/usr/include/SOIL")

find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)
include_directories(${GLEW_INCLUDE_DIRS})
include_directories(${SOIL_INCLUDE_DIRS})
link_libraries(${GLEW_LIBRARIES})


add_executable(OpenGl2 main.cpp)
target_link_libraries(OpenGl2 glfw -lSOIL ${GLFW_LIBRARIES} ${OPENGL_LIBRARIES})
