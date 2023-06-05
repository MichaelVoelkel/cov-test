cmake_minimum_required(VERSION 3.20)

project(src)

find_package(Qt6 COMPONENTS Core REQUIRED)

set(CMAKE_AUTOMOC ON)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fprofile-instr-generate -fcoverage-mapping")

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}")

add_library(src home.cpp home.h)

target_link_libraries(src Qt6::Core)
target_link_options(src PUBLIC -fprofile-instr-generate -fcoverage-mapping)
