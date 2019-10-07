cmake_minimum_required(VERSION 3.14)
project(ImguiTest)

set(CMAKE_CXX_STANDARD 17)
set(GLFW_DEPS X11 Xrandr Xinerama Xxf86vm Xcursor GL dl pthread)
find_package(GLEW REQUIRED)

find_package(OpenGL REQUIRED)
include_directories(${CMAKE_SOURCE_DIR}/imgui)
add_subdirectory(imgui)

add_executable(ImguiTest main.cpp)
target_link_libraries(ImguiTest ImGui GLEW::GLEW ${OPENGL_LIBRARIES} glfw3  ${GLFW_DEPS} ${GLEW_STATIC_LIBRARY})