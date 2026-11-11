cmake_minimum_required(VERSION 3.20)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(udaemon)

add_subdirectory(uipc)
add_subdirectory(uservice)

add_executable(sandbox ${CMAKE_CURRENT_SOURCE_DIR}/src/main.c)

target_link_libraries(sandbox PRIVATE uservice)

