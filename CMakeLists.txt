cmake_minimum_required(VERSION 2.8.10)

project(pi_mc_gmp)

set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)
find_package(GMP REQUIRED)
include_directories(${GMP_INCLUDE_DIR})


set(CMAKE_CXX_FLAGS "-Wall -pipe -std=c++11 -pthread")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -fomit-frame-pointer -march=native")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG}")

set(SRCS
	main.cpp
	)

add_executable(pi_mc_gmp ${SRCS})
target_link_libraries(pi_mc_gmp ${GMPXX_LIBRARIES})
