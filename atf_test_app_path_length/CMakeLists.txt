cmake_minimum_required(VERSION 2.8.3)
project(atf_test_app_path_length)

find_package(catkin REQUIRED COMPONENTS
  atf_core
  atf_test_tools
  roslaunch
  rospy
)
catkin_package(
   CATKIN_DEPENDS rospy
)

###########
## Build ##
###########

#############
## Install ##
#############

install(PROGRAMS scripts/application.py
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

#############
## Testing ##
#############
roslaunch_add_file_check(launch)
atf_test(atf/test_generation_config.yaml)
