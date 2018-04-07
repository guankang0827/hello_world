cmake_minimum_required(VERSION 3.5)

message("Native Build!")
SET(MY_CMAKE_CXX_FLAGS " -std=c++11 -O2 -Wall -fpermissive -g ${CMAKE_CXX_FLAGS}")
PROJECT (cleanpack3)

SET(PLATFORM_NAME "Unix-Like OS")
if(NATIVE_BUILD)
	ADD_DEFINITIONS(-DNATIVE_BUILD)
	SET(CMAKE_SYSTEM_NAME "Generic")
	SET(CMAKE_BUILD_TYPE "Debug")#"Release"
ELSE()
	SET(CMAKE_SYSTEM_NAME "Generic")
	SET(CMAKE_BUILD_TYPE "Release")
ENDIF()
SET(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin_native)
SET(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin_native)

message("-----------------------------------------")
message("Build Platform:  ${PLATFORM_NAME}")
message("Exe Output Path: ${EXECUTABLE_OUTPUT_PATH}")
message("Lib Output Path: ${LIBRARY_OUTPUT_PATH}")
message("CXX FLAGS: ${CMAKE_CXX_FLAGS}")
message("Build Type: ${CMAKE_BUILD_TYPE}")
message("Native Build: ${NATIVE_BUILD}")
message("Send to Target: ${SEND_TO_TARGET_AFTER_BUILD}")

ADD_SUBDIRECTORY(carrier)


