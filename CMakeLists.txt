CMAKE_MINIMUM_REQUIRED(VERSION 3.12) 

PROJECT(terminaltyping)    

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -fopenmp") 

SET(CMAKE_BUILD_TYPE "Debug")  

SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g2 -ggdb") 
SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall") 

add_definitions(-DDEBUG) 

SET(EXECUTABLE_OUTPUT_PATH "${PROJECT_SOURCE_DIR}/bin") 

INCLUDE_DIRECTORIES("${PROJECT_SOURCE_DIR}/include") 

MESSAGE("Identifying the OS...")
if(WIN32)
  MESSAGE("This is Windows.")
elseif(APPLE)
  MESSAGE("This is MacOS.")
elseif(UNIX)
  MESSAGE("This is Linux.")
endif()


AUX_SOURCE_DIRECTORY(src DIR_SRCS) 

add_executable(terminaltyping  
   ${DIR_SRCS}
)