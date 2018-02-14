cmake_minimum_required(VERSION 3.4.3)
project(ProjectB LANGUAGES CXX)

find_package(ProjectA CONFIG REQUIRED a)

add_library(b b.cpp)
target_include_directories(b PUBLIC include PRIVATE ${ProjectA_INCLUDE_DIR})
target_link_libraries(b a)

