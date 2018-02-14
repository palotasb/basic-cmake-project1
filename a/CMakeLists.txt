cmake_minimum_required(VERSION 3.4.3)
project(ProjectA LANGUAGES CXX)

add_library(a a.cpp)
target_include_directories(a PUBLIC include)

set(INCLUDE_INSTALL_DIR ${PROJECT_SOURCE_DIR}/include)

include(CMakePackageConfigHelpers)

configure_package_config_file(ProjectAConfig.cmake.in
    ${CMAKE_CURRENT_BINARY_DIR}/ProjectAConfig.cmake
    INSTALL_DESTINATION ${LIB_INSTALL_DIR}/ProjectA/cmake
    PATH_VARS INCLUDE_INSTALL_DIR)
install(
    FILES ${CMAKE_CURRENT_BINARY_DIR}/ProjectAConfig.cmake
    DESTINATION lib/ProjectA/cmake )

