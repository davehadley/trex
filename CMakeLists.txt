cmake_minimum_required(VERSION 3.10 FATAL_ERROR)

project(trex VERSION 0.1.0)

set(CMAKE_BUILD_TYPE Debug)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(src)
