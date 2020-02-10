cmake_minimum_required(VERSION 3.1.5)
project(plugin-sdk)

set (CMAKE_CXX_STANDARD 17)

include_directories("plugin_sa/")
include_directories("plugin_sa/game_sa")
include_directories("shared/")
include_directories("shared/game")

file(GLOB SOURCES plugin_sa/game_sa/*.cpp shared/*.cpp shared/game/*.cpp shared/extensions/*.cpp)

add_library("plugin_sa" STATIC ${SOURCES})
if (CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
  target_compile_options("plugin_sa" PUBLIC -fpermissive)
endif()
target_compile_definitions("plugin_sa" PUBLIC GTASA)
