cmake_minimum_required(VERSION 2.8.3)
project(pal_text_to_speech_tutorials)

find_package(catkin REQUIRED COMPONENTS
  actionlib
  pal_interaction_msgs
  roscpp
)


catkin_package()

###########
## Build ##
###########

include_directories(
  SYSTEM
  ${catkin_INCLUDE_DIRS}
)


add_executable(tts_client src/tts_client.cpp)
add_dependencies(tts_client ${catkin_EXPORTED_TARGETS})
target_link_libraries(tts_client ${catkin_LIBRARIES})


#############
## Install ##
#############
install(TARGETS tts_client
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
