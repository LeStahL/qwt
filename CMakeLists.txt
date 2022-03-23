cmake_minimum_required(VERSION 3.15)

project(qwt)

set(BUILD_QWT_EXAMPLES OFF CACHE BOOL "Enables build of the examples.")
set(QWT_MOC_INCLUDE ON CACHE BOOL "Enables MOC artifacts inclusion.")

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

find_package(Qt5 COMPONENTS
    Core
    Widgets
    OpenGL
    PrintSupport
    Svg
    Gui
    Concurrent
    
    REQUIRED
)

add_subdirectory(src)

if(BUILD_QWT_EXAMPLES)
    add_subdirectory(examples)
endif()
