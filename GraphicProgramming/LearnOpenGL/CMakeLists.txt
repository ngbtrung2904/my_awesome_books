cmake_minimum_required(VERSION 3.19)
project(HelloGLFW LANGUAGES CXX C)  # Add C language support

find_package(Qt6 6.5 REQUIRED COMPONENTS Core)

qt_standard_project_setup()

# Add GLAD source files
set(GLAD_DIR "${CMAKE_CURRENT_SOURCE_DIR}/glad")
add_library(glad STATIC
    ${GLAD_DIR}/src/glad.c
)
target_include_directories(glad PUBLIC
    ${GLAD_DIR}/include
)

qt_add_executable(HelloGLFW
    # main.cpp
    # hellowindow.cpp
    # hellotriangle.cpp
    shaders.cpp
)

target_include_directories(HelloGLFW PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/inc"
    ${GLAD_DIR}/include
)

target_link_libraries(HelloGLFW PRIVATE
    Qt::Core
    glad
    -lglfw -lGL -ldl
)

include(GNUInstallDirs)

install(TARGETS HelloGLFW
    BUNDLE  DESTINATION .
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
