cmake_minimum_required(VERSION 2.8.3)
project(jr_autonomy_toggler)

find_package(catkin REQUIRED COMPONENTS joy roscpp visualization_msgs interactive_markers rflex)

include_directories(include ${Boost_INCLUDE_DIR} ${catkin_INCLUDE_DIRS})


#set the default path for built executables to the "bin" directory
#set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
#set the default path for built libraries to the "lib" directory
#set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

#uncomment if you have defined messages
#add_message_files(
 # FILES
  # TODO: List your msg files here
#)
#uncomment if you have defined services
#add_service_files(
#  FILES
  # TODO: List your msg files here
#)



include_directories(${Boost_INCLUDE_DIRS})


catkin_package(
    DEPENDS joy roscpp visualization_msgs interactive_markers rflex
    CATKIN_DEPENDS # TODO
    INCLUDE_DIRS # TODO include
    LIBRARIES # TODO
)


add_executable(toggle_joy src/toggle_joy.cpp)
add_dependencies(toggle_joy ${catkin_EXPORTED_TARGETS})
target_link_libraries(toggle_joy ${catkin_LIBRARIES})

add_executable(teleop_marker src/teleop_marker.cpp)
add_dependencies(teleop_marker ${catkin_EXPORTED_TARGETS})
target_link_libraries(teleop_marker ${catkin_LIBRARIES})

## Generate added messages and services with any dependencies listed here
#generate_messages(
#    DEPENDENCIES geometry_msgs std_msgs visualization_msgs
#)

# catkin_package parameters: http://ros.org/doc/groovy/api/catkin/html/dev_guide/generated_cmake_api.html#catkin-package
# TODO: fill in what other packages will need to use this #package





