project(sub2 VERSION 7.8.9)

set(
        SOURCES
        ClassB.cpp
)

set(
        HEADERS
        ../../include/cmake_template/sub2/ClassB.h
        internal.h
)

add_library(
        sub2 STATIC
        ${SOURCES}
        ${HEADERS}
)


include(GNUInstallDirs)
target_include_directories(
        sub2
        PUBLIC
        $<BUILD_INTERFACE:${CMAKE_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}/${CMAKE_PROJECT_NAME}-${CMAKE_PROJECT_VERSION}>
        INTERFACE
        $<BUILD_INTERFACE:${CMAKE_SOURCE_DIR}/src> # for tests
)
