cmake_minimum_required(VERSION 2.8.3)

project(fanuc_lrmate200ib_support)

find_package(catkin REQUIRED)

catkin_package()

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(tests/roslaunch_test.xml)
endif()

foreach(dir config launch meshes urdf)
  install(
    DIRECTORY ${dir}/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach()

install(FILES readme.md DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
