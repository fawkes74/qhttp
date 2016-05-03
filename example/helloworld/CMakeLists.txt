cmake_minimum_required(VERSION 3.0)

project(helloworld)

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME}
  Qt5::Core
  qhttp
)
