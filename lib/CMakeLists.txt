# Copyright: (C) 2015 iCub Facility - Istituto Italiano di Tecnologia
# Authors: Carlo Ciliberto
# CopyPolicy: Released under the terms of the GNU GPL v3.0.

set(headers include/iCub/boostMIL/WeakClassifier.h
            include/iCub/boostMIL/ClassifierInput.h
            include/iCub/boostMIL/ClassifierFactory.h
            include/iCub/boostMIL/MILClassifier.h
            include/iCub/boostMIL/SelectorClassifier.h
            include/iCub/boostMIL/StrongClassifier.h
            include/iCub/boostMIL/OnlineBoost.h
            include/iCub/boostMIL/OnlineSupport.h
            include/iCub/boostMIL/AdaBoost.h
            include/iCub/boostMIL/OnlineSupport.h
            include/iCub/boostMIL/AvgClassifier.h)

set(sources src/MILClassifier.cpp
            src/SelectorClassifier.cpp
            src/StrongClassifier.cpp
            src/OnlineBoost.cpp
            src/OnlineSupport.cpp
            src/AdaBoost.cpp
            src/AvgClassifier.cpp)

source_group("Header Files" FILES ${headers})
source_group("Source Files" FILES ${sources})

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include ${YARP_INCLUDE_DIRS})
add_library(boostMIL ${headers} ${sources})
target_link_libraries(boostMIL ${YARP_LIBRARIES})

icubcontrib_export_library(boostMIL INTERNAL_INCLUDE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}/include
                                    EXTERNAL_INCLUDE_DIRS ${YARP_INCLUDE_DIRS}
                                    DESTINATION include/iCub/boostMIL
                                    FILES ${headers})
