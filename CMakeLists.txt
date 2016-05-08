cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unknown-pragmas")

if (NOT TARGET http-parser AND IS_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/3rdparty/http-parser)
  add_library(http-parser STATIC
    3rdparty/http-parser/http_parser.c
    3rdparty/http-parser/http_parser.h
  )

  target_include_directories(http-parser PUBLIC
    3rdparty/http-parser
    3rdparty
  )
endif()

find_package(Qt5Core REQUIRED)
find_package(Qt5Network REQUIRED)

add_subdirectory(src)
add_subdirectory(example)
