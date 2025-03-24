# Download and include Google Test
include(FetchContent)
FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG        v1.16.0
)
FetchContent_MakeAvailable(googletest)

# For Windows: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

# Enable testing
enable_testing()

# Collect all .cpp files in tests/
file(GLOB TEST_SOURCES *.cpp)

# Only add the test executable if there are test files
if(TEST_SOURCES)
    # Add test executable
    add_executable(runTests ${TEST_SOURCES})

    # Link Google Test, GMock, and sources library
    target_link_libraries(runTests
        PRIVATE
        sources_lib
        GTest::gtest_main
        GTest::gmock_main
    )

    # Add include directories for headers and Google Mock
    include_directories(
        ${CMAKE_SOURCE_DIR}/header
        ${gtest_SOURCE_DIR}/include
        ${gtest_SOURCE_DIR}/../googlemock/include
    )

    # Register tests with CTest
    include(GoogleTest)
    gtest_discover_tests(runTests)
endif()
