cmake_minimum_required(VERSION 3.26)
project(Test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set (CMAKE_CXX_SCAN_FOR_MODULES ON)
#set(CMAKE_CXX_MODULE_STD 1)
add_executable(Test)

# Add module files here
target_sources(Test
PRIVATE 
    FILE_SET CXX_MODULES FILES
)

# Add non module files (no exports) here
target_sources(Test 
PRIVATE
    src/main.cpp
)
target_link_libraries(Test PRIVATE stdc++exp)