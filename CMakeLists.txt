cmake_minimum_required(VERSION 3.5.1)

project(template)

set(CMAKE_PREFIX_PATH /usr)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)
find_package(PkgConfig REQUIRED)

# $ pkg-config --cflags dtkcore dtkwidget
pkg_check_modules(DTK REQUIRED dtkcore dtkwidget)

if (${DTK_FOUND})
    message("-" " Found DTK!")
else()
    message(FATAL_ERROR "-" " Not Found DTK! Please install it!")
endif()

message("-" " Found BUILD_BINARY_DIR:   " ${CMAKE_BINARY_DIR})
message("-" " Found BUILD_SOURCE_DIR:   " ${CMAKE_SOURCE_DIR})
message("-" " Found Qt5Core version:    " ${Qt5Core_VERSION})
message("-" " Found Qt5Widgets version: " ${Qt5Widgets_VERSION})
message("-" " Found CMAKE_CURRENT_BINARY_DIR: " ${CMAKE_CURRENT_BINARY_DIR})
message("-" " Found CMAKE_CURRENT_SOURCE_DIR: " ${CMAKE_CURRENT_SOURCE_DIR})
message("-" " Found CMAKE_INSTALL_PREFIX:     " ${CMAKE_INSTALL_PREFIX})

