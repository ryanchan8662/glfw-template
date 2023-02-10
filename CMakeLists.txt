cmake_minimum_required(VERSION 3.23)
project(glfw-template)

if (WIN32)
    set(glfw3_DIR C:/msys64/mingw64/lib/cmake/glfw3)
endif()

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)

set(CMAKE_CXX_STANDARD 17)

add_executable(main main.cpp)
target_link_libraries(main glfw)
target_link_libraries(main ${OPENGL_LIBRARIES})

if (APPLE)
    target_link_libraries(main "-framework OpenGL")
endif()
