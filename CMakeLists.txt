project(Application-Framework)
cmake_minimum_required(VERSION 3.0)
set (CMAKE_CXX_STANDARD 11)


add_library(Application-Framework STATIC Source/AppFramework.cpp Source/AppFramework.hpp)

target_include_directories(Application-Framework INTERFACE Source/include)
