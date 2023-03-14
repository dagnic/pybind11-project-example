cmake_minimum_required(VERSION 3.15)

project(pybind11_project_example)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_VERBOSE_MAKEFILE ON)

find_package(Python3 REQUIRED COMPONENTS Interpreter Development)
if (PYTHONLIBS_FOUND)
    include_directories(${PYTHON_INCLUDE_DIRS})
    message("Using default python version: " ${PYTHONLIBS_VERSION_STRING})
endif()

message("CMake module path: " ${CMAKE_MODULE_PATH})
find_package(pybind11 REQUIRED)

file(GLOB_RECURSE SOURCES src/**.cpp)
add_library(cpp_library SHARED ${SOURCES})
add_subdirectory(src)
add_subdirectory(cpp_library_bindings)

install(TARGETS cpp_library DESTINATION scikit_build_example)
install(TARGETS _core DESTINATION scikit_build_example)
