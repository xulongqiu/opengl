cmake_minimum_required (VERSION 3.5)

project (openglsetup)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Werror -std=c++11")
set (source_dir "${PROJECT_SOURCE_DIR}/src")

file (GLOB source_files "${source_dir}/*.cpp")

set (LIBS
    libGL.so
    libGLU.so
    libglut.so
    )

add_executable (setup ${source_files})
target_link_libraries(setup -Wl,--start-group ${LIBS})
