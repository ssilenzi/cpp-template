cmake_minimum_required(VERSION 3.21)
project(cpp)

set(CMAKE_CXX_STANDARD 23)

# Enable globbing to search for source files
file(GLOB_RECURSE SOURCES "src/*.cpp")

# Iterate over each source file
foreach(SOURCE ${SOURCES})
    # Get the file name without extension
    get_filename_component(EXECUTABLE_NAME ${SOURCE} NAME_WE)

    # Create an executable target with the same name as the source file
    add_executable(${EXECUTABLE_NAME} ${SOURCE})
endforeach()

# Export compile commands for tooling
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
