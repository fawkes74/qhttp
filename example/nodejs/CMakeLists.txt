cmake_minimum_required(VERSION 3.0)

project(nodejs)

add_executable(${PROJECT_NAME} main.cpp
  ../include/gason.cpp
  ../include/gason.hpp
  ../include/jsonbuilder.hpp
)

target_link_libraries(${PROJECT_NAME}
  Qt5::Core
  qhttp
)
