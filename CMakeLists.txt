cmake_minimum_required(VERSION 3.10)
project(jenkinsexample)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTORCC ON)
set(CMAKE_PREFIX_PATH /usr/local/Qt-5.15.0/lib/cmake/Qt5)
find_package(Catch2 QUIET)

set(CMAKE_CXX_STANDARD 11)

add_executable(jenkinsexample main.cpp helloWorld.cpp helloWorld.h)

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)

target_compile_definitions(jenkinsexample PRIVATE $<$<OR:$<CONFIG:Debug>,$<CONFIG:RelWithDebInfo>>:QT_QML_DEBUG>)
target_link_libraries(jenkinsexample PRIVATE Qt5::Core Qt5::Widgets)



