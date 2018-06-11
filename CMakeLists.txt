cmake_minimum_required(VERSION 2.8.9)
project (hello)
#set(CMAKE_BUILD_TYPE Debug)



set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake_modules)
find_package(SQLite3 REQUIRED)
set(${SQLITE3_INCLUDE_DIRS})

find_package(Boost 1.36.0)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
endif()


#include (cmake_modules/sqlite3Config.cmake)

# Add a custom CMake Modules directory
#set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake_modules")


add_executable(main src/main.cpp)
target_link_libraries(main ${SQLITE3_LIBRARIES})
