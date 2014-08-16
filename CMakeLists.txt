cmake_minimum_required(VERSION 2.8)

project(ogg C) 

#
# Config
#

set(ogg_VERSION 1.3.2)

#
# Internal
#


#
# Build Library
#
include_directories("include/")
file(GLOB_RECURSE ogg_HEADERS include/*.h)
file(GLOB_RECURSE ogg_SOURCES src/*.c ${ogg_HEADERS})
add_library(ogg ${ogg_SOURCES})

install(TARGETS ${PROJECT_NAME} 
		DESTINATION ${CMAKE_INSTALL_PREFIX}/lib 
		COMPONENT ${PROJECT_NAME}
)

install(FILES ${ogg_HEADERS} 
		DESTINATION ${CMAKE_INSTALL_PREFIX}/include/${PROJECT_NAME}
)
