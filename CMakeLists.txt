cmake_minimum_required(VERSION 3.31)

set(MY_PROJECT_NAME "template_project")

project(${MY_PROJECT_NAME})
add_executable(${MY_PROJECT_NAME})

target_include_directories(${MY_PROJECT_NAME} PRIVATE headers)

add_subdirectory(sources)
add_subdirectory(app)

