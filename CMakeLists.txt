cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wno-unknown-pragmas")

add_library(http-parser STATIC
  3rdparty/http-parser/http_parser.c
  3rdparty/http-parser/http_parser.h
)

target_include_directories(http-parser PUBLIC
  3rdparty/http-parser
  3rdparty
)

find_package(Qt5Core REQUIRED)
find_package(Qt5Network REQUIRED)


add_subdirectory(src)
add_subdirectory(example)
