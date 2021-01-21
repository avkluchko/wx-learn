cmake_minimum_required(VERSION 3.17)
project(wx_learn)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -Wall -Werror")

add_subdirectory(libs/wxWidgets)
add_executable(helloworld src/01-helloworld/main.cpp)
target_link_libraries(helloworld wx::core)

# все для тестирования
add_subdirectory(libs/googletest)
include_directories(libs/googletest/googletest/include)
add_executable(all_tests tests/all_tests.cpp)
target_link_libraries(all_tests gtest gtest_main)
