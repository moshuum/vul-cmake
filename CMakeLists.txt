cmake_minimum_required(VERSION 2.8.9)
project (hello)
#set(CMAKE_BUILD_TYPE Debug)


# Add a custom CMake Modules directory
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules")

add_executable(helloapp src/helloworld.cpp)

find_package(sqlite3)

#set (ALL_SQLITE_TARGETS)

#add_subdirectory(subproject1)
#add_subdirectory(subproject2)



if (SQLITE3_FOUND)
  include_directories(${SQLITE3_INCLUDE_DIRS})
  target_link_libraries (hello ${SQLITE3_LIBRARIES})
  message("sqlite found ${SQLITE3_INCLUDE_DIRS}")
endif (SQLITE3_FOUND)


#add_executable(helloapp src/helloworld.cpp)
