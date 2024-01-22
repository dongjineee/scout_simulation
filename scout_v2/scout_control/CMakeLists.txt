cmake_minimum_required(VERSION 2.8.3)
project(scout_control)

find_package(catkin REQUIRED COMPONENTS 
    rospy
    geometry_msgs
    roslaunch)

catkin_python_setup()
catkin_package(
  CATKIN_DEPENDS rospy geometry_msgs
)

roslaunch_add_file_check(launch)

catkin_install_python(PROGRAMS
  node/key_scout_teleop
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY config launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
