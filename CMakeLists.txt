cmake_minimum_required(VERSION 3.15)
project(HelloWorld LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(hello main.cpp)

enable_testing()
add_test(NAME hello_output COMMAND hello)
set_tests_properties(hello_output PROPERTIES PASS_REGULAR_EXPRESSION "Hello, World!")
