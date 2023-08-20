project(imgui_tex_inspect)

set(IMGUI_TEX_INSPECT_SRC
   backends/tex_inspect_opengl.cpp
   backends/tex_inspect_opengl.h
   imgui_tex_inspect.cpp
   imgui_tex_inspect.h
   imgui_tex_inspect_internal.h
)

add_library(imgui_tex_inspect STATIC ${IMGUI_TEX_INSPECT_SRC})
target_include_directories(imgui_tex_inspect PUBLIC . backends)
target_compile_definitions(imgui_tex_inspect PRIVATE IMGUI_IMPL_OPENGL_LOADER_GL3W)

target_link_libraries(imgui_tex_inspect glfw gl3w imgui)
