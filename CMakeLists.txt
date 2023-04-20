cmake_minimum_required(VERSION 3.20)
# Change template to your own project name
project(template)

set(CMAKE_CXX_STANDART 14)

# Version numbers might change in the future check your folder
# names you can go to these folders using command + g and typing
# /opt/homebrew while you are in finder
include_directories(/opt/homebrew/Cellar/glfw/3.3.8/include)
link_directories(/opt/homebrew/Cellar/glfw/3.3.8/lib)

#include glad
set(GLAD_DIR ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glad)
include_directories(${GLAD_DIR}/include)
aux_source_directory(${GLAD_DIR}/src GLAD_SOURCE)

#include main 
aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR}/src MAIN_SOURCE)

# We include our source files here
add_executable(template ${MAIN_SOURCE} ${GLAD_SOURCE})

# Link the necessary libraries
find_package(OpenGL REQUIRED)
target_link_libraries(template PRIVATE OpenGL::GL)
find_package(glfw3 REQUIRED)
target_link_libraries(template PRIVATE glfw.3.3)