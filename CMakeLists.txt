cmake_minimum_required(VERSION 3.16)
project(imgui)

add_library(imgui)
target_sources(imgui PRIVATE 
"${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/imgui_freetype.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp"
"${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_vulkan.cpp")

target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/)

find_package(Freetype REQUIRED)
target_link_libraries(imgui  PRIVATE Freetype::Freetype)