cmake_minimum_required(VERSION 2.8.3)
project(scout_gazebo)

find_package(catkin REQUIRED COMPONENTS)

catkin_package()


install(
  DIRECTORY worlds
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(
  FILES launch/scout_empty_world.launch
        launch/scout_playpen.launch
        launch/playpen.launch
        launch/spawn_scout.launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/scout_empty_world.launch)
  roslaunch_add_file_check(launch/scout_playpen.launch)
  roslaunch_add_file_check(launch/playpen.launch)
  roslaunch_add_file_check(launch/spawn_scout.launch)
endif()