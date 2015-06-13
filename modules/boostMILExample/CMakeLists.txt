# Copyright: (C) 2015 iCub Facility - Istituto Italiano di Tecnologia
# Authors: Carlo Ciliberto
# CopyPolicy: Released under the terms of the GNU GPL v3.0.

set(PROJECTNAME boostMILExample)
project(${PROJECTNAME})

set(sources src/main.cpp)
source_group("Source Files" FILES ${sources})

include_directories(${boostMIL_INCLUDE_DIRS} ${YARP_INCLUDE_DIRS})
add_executable(${PROJECTNAME} ${sources})
target_link_libraries(${PROJECTNAME} boostMIL ${YARP_LIBRARIES})
install(TARGETS ${PROJECTNAME} DESTINATION bin)

# app
file(GLOB conf ${CMAKE_CURRENT_SOURCE_DIR}/app/conf/*.ini)
yarp_install(FILES ${conf} DESTINATION ${ICUBCONTRIB_CONTEXTS_INSTALL_DIR}/${PROJECTNAME})
