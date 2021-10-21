cmake_minimum_required(VERSION 3.4.3 FATAL_ERROR)

project(test CXX)

add_executable(test main.cpp)

set(CPACK_STRIP_FILES TRUE)
set(CPACK_GENERATOR "ZIP")

install(TARGETS test)

include(CPack)
