find_package(OpenGL REQUIRED)


include_directories(
    include
    ${OPENGL_INCLUDE_DIR}
    ${K4A_INCLUDE_DIRS}
)

add_executable(opengl_viewer
    src/main.cpp
    src/texture.cpp
    src/viewerwindow.cpp
)

target_link_libraries(opengl_viewer PRIVATE
    k4a::k4a
    glfw::glfw
    imgui::imgui)