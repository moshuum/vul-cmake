# Set the project name
project (subproject2)

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    main2.cpp
)

# include the file with the function then call the macro
include(${CMAKE_SOURCE_DIR}/cmake/modules/sqlite3.cmake)
add_sqlite(${PROJECT_NAME} SOURCES)

# Add an executable with the above sources
add_executable(${PROJECT_NAME} ${SOURCES})
