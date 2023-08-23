cmake_minimum_required(VERSION 2.8)
project (mqtt.embedded.demo)
set(CMAKE_BUILD_TYPE Debug)

message(STATUS "CMake version: " ${CMAKE_VERSION})
message(STATUS "CMake system name: " ${CMAKE_SYSTEM_NAME})

## build settings
set(PAHO_VERSION_MAJOR 1)
set(PAHO_VERSION_MINOR 0)
set(PAHO_VERSION_PATCH 0)
set(CLIENT_VERSION ${PAHO_VERSION_MAJOR}.${PAHO_VERSION_MINOR}.${PAHO_VERSION_PATCH})

string(TIMESTAMP BUILD_TIMESTAMP UTC)
message(STATUS "Timestamp is ${BUILD_TIMESTAMP}")

include_directories(MQTTPacket/src)
include_directories(MQTTClient/src)

enable_testing()
ADD_SUBDIRECTORY(MQTTPacket)

add_executable(hello hello.cpp)
# target_link_libraries(hello MQTTPacketClient)