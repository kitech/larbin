project(larbin)
    
cmake_minimum_required(VERSION 2.8)
set(CMAKE_VERBOSE_MAKEFILE on)
set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS "-std=c++0x")

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR})

#### auto configure adns subproject
find_file(ADNS_CFGED config.h PATHS "${PROJECT_SOURCE_DIR}/adns" NO_DEFAULT_PATH)
#message(${ADNS_CFGED} " abcde" ${ADNS_CFGED-NOTFOUND} "xy")
if(ADNS_CFGED)
    #message("ok found")
else(ADNS_CFGED)
    #message("not found")
    execute_process(COMMAND "${PROJECT_SOURCE_DIR}/adns/configure" WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}/adns"
                            TIMDOUT 10 OUTPUT_QUIET)
endif(ADNS_CFGED)

add_subdirectory(adns)
add_subdirectory(src)

# add_executable(larbin main.cpp)

