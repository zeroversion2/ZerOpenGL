cmake_minimum_required(VERSION 3.16)
project(ZerOpenGL)

set(CMAKE_CXX_STANDARD 14)

if (WIN32)
    set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
    set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
    set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
    add_subdirectory(glfw)
else()
    find_package(glfw3)
endif ()

add_executable(ZerOpenGL glad.c main.cpp)

target_include_directories(ZerOpenGL PUBLIC include)
target_link_libraries(ZerOpenGL glfw)