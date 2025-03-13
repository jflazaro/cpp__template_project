# Collect all .cpp files in sources/
file(GLOB SOURCES *.cpp)

# If there are source files, create the library
if(SOURCES)
    add_library(sources_lib ${SOURCES})
    target_include_directories(sources_lib PUBLIC ${CMAKE_SOURCE_DIR}/header)
else()
    # If no source files exist, create an empty interface library
    add_library(sources_lib INTERFACE)
    target_include_directories(sources_lib INTERFACE ${CMAKE_SOURCE_DIR}/header)
endif()
