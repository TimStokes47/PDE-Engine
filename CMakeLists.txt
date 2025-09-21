cmake_minimum_required(VERSION 3.26)
project(Test LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set (CMAKE_CXX_SCAN_FOR_MODULES ON)
enable_testing()

add_executable(PDE_Engine)

# Add module files here
target_sources(PDE_Engine
PRIVATE 
    FILE_SET CXX_MODULES FILES
)

# Add non module files (no exports) here
target_sources(PDE_Engine 
PRIVATE
    src/main.cpp
)
target_link_libraries(PDE_Engine PRIVATE stdc++exp)

add_subdirectory(tests)