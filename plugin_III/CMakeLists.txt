cmake_minimum_required(VERSION 3.1.5)
project(plugin_III)

set (CMAKE_CXX_STANDARD 17)

file(GLOB SOURCES game_III/*.cpp ../shared/*.cpp ../shared/game/*.cpp ../shared/extensions/*.cpp)
add_library(${PROJECT_NAME} STATIC ${SOURCES})

if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
  target_compile_options(${PROJECT_NAME} PUBLIC -fpermissive)
endif()

target_compile_definitions(${PROJECT_NAME} PUBLIC GTA3)

target_include_directories(${PROJECT_NAME} PUBLIC "./")
target_include_directories(${PROJECT_NAME} PUBLIC "./game_III/")
target_include_directories(${PROJECT_NAME} PUBLIC "../shared/")
target_include_directories(${PROJECT_NAME} PUBLIC "../shared/game")
