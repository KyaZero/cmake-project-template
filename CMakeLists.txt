cmake_minimum_required(VERSION 3.21)

project("cmake-project-template" VERSION "0.0.1" LANGUAGES CXX)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)
set_property(GLOBAL PROPERTY PREDEFINED_TARGETS_FOLDER "predefined")

include("cmake/compiler_features.cmake")
include("cmake/compiler_warnings.cmake")
include("cmake/auto_group_sources.cmake")

set(${PROJECT_NAME}_FOLDER
    ${PROJECT_NAME}
    CACHE STRING "The folder that ${PROJECT_NAME} projects will be placed in.")

add_subdirectory("extern")
add_subdirectory("app")

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT "app")