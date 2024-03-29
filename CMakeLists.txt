cmake_minimum_required(VERSION 3.20)
# Change template to your own project name
project(template)

set(CMAKE_CXX_STANDART 14)
#在cmake中有一个全局的环境变量，CMAKE_BUILD_TYPE，可以取Release或者Debug等值。然后可以通过设置CMAKE_CXX_FLAGS_DEBUG来设置在debug时的CXXFLAGS
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAG_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb")
set(CMAKE_CXX_FLAG_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")

# Version numbers might change in the future check your folder
# names you can go to these folders using command + g and typing
# /opt/homebrew while you are in finder
include_directories(/opt/homebrew/Cellar/glfw/3.3.8/include)
link_directories(/opt/homebrew/Cellar/glfw/3.3.8/lib)
# include_directories(/opt/homebrew/Cellar/glew/2.2.0_1/include)
# link_directories(/opt/homebrew/Cellar/glew/2.2.0_1/lib)

#include glad
set(GLAD_DIR ${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glad)
include_directories(${GLAD_DIR}/include)
aux_source_directory(${GLAD_DIR}/src GLAD_SOURCE)

#include glm
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/thirdparty/glm)

#include main 
aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR}/src MAIN_SOURCE)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src())

# We include our source files here
add_executable(template ${MAIN_SOURCE} ${GLAD_SOURCE})

# Link the necessary libraries
# find_package(OpenGL REQUIRED)
# target_link_libraries(template PRIVATE OpenGL::GL)
find_package(glfw3 REQUIRED)
target_link_libraries(template PRIVATE glfw.3.3)
# find_package(GLEW REQUIRED)
# target_link_libraries(template PRIVATE GLEW)
find_package(glm REQUIRED)
target_link_libraries(template PRIVATE glm)