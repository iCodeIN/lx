cmake_minimum_required(VERSION 3.0.0)

project(lx)

set(EXEC lx)

set (CMAKE_CXX_STANDARD 17)
set (CMAKE_CXX_STANDARD_REQUIRED ON)
set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -O3")

if (NOT WIN32)
  set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wextra -Wshadow -Wconversion -Wfatal-errors")
endif()

set (CMAKE_EXPORT_COMPILE_COMMANDS ON)

include_directories(includes)
file(GLOB SOURCES src/*)

add_executable(${EXEC} ${SOURCES})
install(TARGETS ${EXEC} DESTINATION /usr/local/bin)
