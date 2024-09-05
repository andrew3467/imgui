cmake_minimum_required(VERSION 3.27)
project(ImGui)

set(CMAKE_CXX_STANDARD 23)

set(SOURCE
        imgui_widgets.cpp
        imgui_tables.cpp
        imgui.cpp
        imgui_demo.cpp
        imgui_draw.cpp
)

set(HEADERS
        imstb_truetype.h
        imstb_textedit.h
        imstb_rectpack.h
        imgui_internal.h
        imgui.h
        imconfig.h
)

file(GLOB_RECURSE BACKENDS backends/*.h backends/*.cpp)


add_library(ImGui
        ${SOURCE}
        ${HEADERS}
        ${BACKENDS}
)