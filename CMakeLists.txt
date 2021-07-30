cmake_minimum_required(VERSION 3.21.0)

#get folder name
get_filename_component(FolderName ${CMAKE_CURRENT_SOURCE_DIR} NAME)

#set project name as folder name
project(${FolderName} VERSION 1.0)
message("Project name: ${PROJECT_NAME}")

set(CXX_STANDARD 14)
set(CXX_STANDARD_REQUIRED True)

file(GLOB CppFiles "./*.cpp")

add_executable(${PROJECT_NAME} ${CppFiles})

target_include_directories(${PROJECT_NAME} PUBLIC "./include/")


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
