cmake_minimum_required(VERSION 3.31)

# Project name
set(MY_PROJECT_NAME "main")
project(${MY_PROJECT_NAME})

# Set C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Add include directory for headers/
include_directories(${CMAKE_SOURCE_DIR}/headers)

# Add subdirectories for sources/ and tests/
add_subdirectory(sources)
add_subdirectory(tests)

# Add executable from app/
add_executable(${MY_PROJECT_NAME} app/main.cpp)

# Link the sources library to the executable.
target_link_libraries(${MY_PROJECT_NAME} sources_lib)
