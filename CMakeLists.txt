cmake_minimum_required(VERSION 3.17)
project(wx_learn)

set(CMAKE_CXX_STANDARD 17)

add_executable(main src/main.cpp)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -Wall -Werror")
add_subdirectory(lib/googletest)

# все для тестирования
include_directories(lib/googletest/googletest/include)
add_executable(all_tests tests/all_tests.cpp)
target_link_libraries(all_tests gtest gtest_main)
