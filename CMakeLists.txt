cmake_minimum_required(VERSION 2.8.9)
project (hello)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake_modules)
find_package(SQLite3 REQUIRED)
set(${SQLITE3_INCLUDE_DIRS})

find_package(Boost 1.36.0)
if(Boost_FOUND)
  include_directories(${Boost_INCLUDE_DIRS})
endif()

add_executable(main src/main.cpp)
target_link_libraries(main ${SQLITE3_LIBRARIES} ${Boost_LIBRARIES} )
