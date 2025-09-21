# Install Google Test from GitHub
include(FetchContent)
FetchContent_Declare(
  GTest 
  GIT_REPOSITORY https://github.com/google/googletest.git
  GIT_TAG v1.17.0
)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(GTest)

# Add test files here
add_executable(
  UnitTests
  test.cpp
)

target_link_libraries(
  UnitTests PRIVATE GTest::gtest_main
)

include(CTest)
include(GoogleTest)
gtest_discover_tests(UnitTests)