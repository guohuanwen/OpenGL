cmake_minimum_required(VERSION 3.20)
# Change template to your own project name
project(template)

set(CMAKE_CXX_STANDART 14)

# Version numbers might change in the future check your folder
# names you can go to these folders using command + g and typing
# /opt/homebrew while you are in finder
include_directories(/opt/homebrew/Cellar/glew/2.2.0_1/include)
include_directories(/opt/homebrew/Cellar/glfw/3.3.4/include)
link_directories(/opt/homebrew/Cellar/glew/2.2.0_1/lib)
link_directories(/opt/homebrew/Cellar/glfw/3.3.4/lib)

# We include our source files here
add_executable(template src/main.cpp)

# Link the necessary libraries
find_package(OpenGL REQUIRED)
target_link_libraries(template PRIVATE OpenGL::GL)
find_package(glfw3 REQUIRED)
target_link_libraries(template PRIVATE glfw.3.3)
find_package(GLEW REQUIRED)
target_link_libraries(template PRIVATE GLEW)