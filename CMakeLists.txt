cmake_minimum_required(VERSION 3.13)
cmake_policy(SET CMP0076 NEW)
if (${CMAKE_VERSION} VERSION_GREATER "3.24")
    cmake_policy(SET CMP0135 OLD)
endif()

project( VERSION 0.1.0)

set(CMAKE_CXX_STANDARD 20)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")
include(declare_and_apply_options.cmake)

add_subdirectory(src)

if (ENABLE_TEST)
    add_subdirectory(tests)
endif()
