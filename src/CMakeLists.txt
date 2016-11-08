cmake_minimum_required(VERSION 3.0)

project(qhttp)

add_library(${PROJECT_NAME} STATIC
  qhttpabstracts.cpp
  qhttpabstracts.hpp
  qhttpclient.cpp
  qhttpclient.hpp
  qhttpclientrequest.cpp
  qhttpclientrequest.hpp
  qhttpclientresponse.cpp
  qhttpclientresponse.hpp
  qhttpfwd.hpp
  qhttpserverconnection.cpp
  qhttpserverconnection.hpp
  qhttpserver.cpp
  qhttpserver.hpp
  qhttpserverrequest.cpp
  qhttpserverrequest.hpp
  qhttpserverresponse.cpp
  qhttpserverresponse.hpp
  private/qhttpbase.hpp
  private/qhttpclient_private.hpp
  private/qhttpclientrequest_private.hpp
  private/qhttpclientresponse_private.hpp
  private/qhttpserver_private.hpp
  private/qhttpserverconnection_private.hpp
  private/qhttpserverrequest_private.hpp
  private/qhttpserverresponse_private.hpp
)

target_link_libraries(${PROJECT_NAME}
  Qt5::Core
  Qt5::Network
  http-parser
)

target_include_directories(${PROJECT_NAME}
  PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}
  PRIVATE
  ${CMAKE_CURRENT_SOURCE_DIR}/private
)

target_compile_features(${PROJECT_NAME} PUBLIC cxx_nullptr)

set_target_properties(${PROJECT_NAME} PROPERTIES
  AUTOMOC ON
)

target_compile_definitions(${PROJECT_NAME} PUBLIC QHTTP_EXPORT=1)
