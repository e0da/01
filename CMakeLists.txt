cmake_minimum_required(VERSION 2.6)

set(BIN 01)
project(${BIN})

file(GLOB SOURCES *.c)
file(GLOB HEADERS *.h)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})
include_directories(${SDL2_IMAGE_INCLUDE_DIR})

add_executable(${BIN} ${SOURCES})
target_link_libraries(${BIN} ${SDL2_LIBRARIES})
target_link_libraries(${BIN} ${SDL2_IMAGE_LIBRARY})
