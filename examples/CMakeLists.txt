cmake_minimum_required(VERSION 3.0)
project(hunter_test_case_0-examples)

if(TARGET hunter_test_case_0)
  add_library(hunter_test_case_0::hunter_test_case_0 ALIAS hunter_test_case_0)
else()
  find_package(hunter_test_case_0 CONFIG REQUIRED)
endif()

add_executable(foo foo.cpp)
target_link_libraries(foo PUBLIC hunter_test_case_0::hunter_test_case_0)

enable_testing()
add_test(NAME TestFoo COMMAND foo)
