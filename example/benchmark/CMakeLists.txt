cmake_minimum_required(VERSION 3.0)

project(benchmark)

add_executable(${PROJECT_NAME}
  main.cpp
  ../include/gason.cpp
  ../include/gason.hpp
  server.cpp
  server.hpp
  clients.cpp
  clients.hpp
)

target_link_libraries(${PROJECT_NAME}
  Qt5::Core
  qhttp
)

set_target_properties(${PROJECT_NAME} PROPERTIES
  AUTOMOC ON
)

target_include_directories(${PROJECT_NAME}
  PRIVATE
  ${CMAKE_CURRENT_BINARY_DIR}
)
