# Generated from simplechat.pro.

cmake_minimum_required(VERSION 3.14)
project(chatserver LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(INSTALL_EXAMPLEDIR "examples/websockets/simplechat")

find_package(Qt6 COMPONENTS WebSockets)

add_executable(chatserver
    chatserver.cpp chatserver.h
    main.cpp
)
target_link_libraries(chatserver PUBLIC
    Qt::WebSockets
)

install(TARGETS chatserver
    RUNTIME DESTINATION "${INSTALL_EXAMPLEDIR}"
    BUNDLE DESTINATION "${INSTALL_EXAMPLEDIR}"
    LIBRARY DESTINATION "${INSTALL_EXAMPLEDIR}"
)
