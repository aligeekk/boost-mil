# Copyright: (C) 2015 iCub Facility - Istituto Italiano di Tecnologia
# Authors: Carlo Ciliberto
# CopyPolicy: Released under the terms of the GNU GPL v3.0.

cmake_minimum_required(VERSION 2.8)

if(COMMAND cmake_policy)
    cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

project(boostMIL)

find_package(YARP REQUIRED)
find_package(ICUBcontrib REQUIRED)
list(APPEND CMAKE_MODULE_PATH ${YARP_MODULE_PATH})
list(APPEND CMAKE_MODULE_PATH ${ICUBCONTRIB_MODULE_PATH})

include(YarpInstallationHelpers)
include(ICUBcontribHelpers)
include(ICUBcontribOptions)

icubcontrib_set_default_prefix()
add_definitions(${YARP_DEFINES})

add_subdirectory(lib)
add_subdirectory(modules)

icubcontrib_finalize_export(boostMIL)
icubcontrib_add_uninstall_target()
