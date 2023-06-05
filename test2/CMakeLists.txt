cmake_minimum_required(VERSION 3.20)

project(test2)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fprofile-instr-generate -fcoverage-mapping")

include_directories(../src)

find_package(Qt6 COMPONENTS Test REQUIRED)

set(CMAKE_AUTOMOC ON)

find_library(SRC_LIB NAMES src PATHS ../build/src REQUIRED)

add_executable(test home.t.cpp)
target_link_libraries(test ${SRC_LIB} Qt6::Test)

target_link_options(test PUBLIC -fprofile-instr-generate -fcoverage-mapping)