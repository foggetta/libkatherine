cmake_minimum_required(VERSION 3.0)
project(katherine LANGUAGES C CXX)

option(BUILD_CXX        "build C++ binaries"        ON)
option(BUILD_PYTHON     "build Python 3 bindings"   OFF)
option(BUILD_EXAMPLES   "build example programs"    ON)

set(CMAKE_C_STANDARD    11)
set(CMAKE_CXX_STANDARD  14)

set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

add_subdirectory(c)

if(BUILD_CXX)
    add_subdirectory(cxx)
endif(BUILD_CXX)

if(BUILD_PYTHON)
    add_subdirectory(python)
endif(BUILD_PYTHON)

