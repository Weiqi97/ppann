# Set cmake version.
cmake_minimum_required(VERSION 3.24)

# Project name and language.
project(
        PPANN
        VERSION 0.1
        DESCRIPTION "This project implements the inner product revealing encryption."
        LANGUAGES C
)

# Set standards and include tests.
if (CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
    set(CMAKE_C_STANDARD 17)
    set_property(GLOBAL PROPERTY USE_FOLDERS ON)
    include(CTest)
endif()

# Find the relic library.
find_library(RELIC_LIB relic)

# Add desired subdirectories.
add_subdirectory(src)
add_subdirectory(apps)
add_subdirectory(tests)