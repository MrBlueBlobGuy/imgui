cmake_minimum_required(VERSION 3.10)
project(dear_imgui LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Path to Dear ImGui sources
set(IMGUI_DIR ${CMAKE_CURRENT_SOURCE_DIR})

# Core ImGui source files
set(IMGUI_SOURCES
    ${IMGUI_DIR}/imgui.cpp
    ${IMGUI_DIR}/imgui_demo.cpp
    ${IMGUI_DIR}/imgui_draw.cpp
    ${IMGUI_DIR}/imgui_tables.cpp
    ${IMGUI_DIR}/imgui_widgets.cpp
)

# Create a backend-agnostic static library
add_library(dear_imgui STATIC ${IMGUI_SOURCES})

# Make includes available for projects linking this library
target_include_directories(dear_imgui PUBLIC
    ${IMGUI_DIR}
)
