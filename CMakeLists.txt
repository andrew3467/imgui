cmake_minimum_required(VERSION 3.27)
project(ImGui)

set(CMAKE_CXX_STANDARD 20)

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

set(BACKENDS
        backends/imgui_impl_sdl3.cpp
        backends/imgui_impl_sdl3.h
        backends/imgui_impl_sdlrenderer3.cpp
        backends/imgui_impl_sdlrenderer3.h
)

include_directories(.)


add_library(ImGui
        ${SOURCE}
        ${HEADERS}
        ${BACKENDS}
)

target_link_libraries(
        ImGui
        PUBLIC
        SDL3::SDL3
)