cmake_minimum_required(VERSION 3.0)
project(MyProject C)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(pwd ${CMAKE_CURRENT_SOURCE_DIR})
set(RAYLIB_DIR ${pwd}/lib/raylib)
set(src ${pwd}/src)

include_directories(
    ${RAYLIB_DIR}/include
    ${src}
)

add_executable(my_program
    ${src}/main.c
)

target_link_libraries(my_program
    ${RAYLIB_DIR}/lib/libraylib.a
    "-framework Cocoa"
    "-framework OpenGL"
    "-framework IOKit"
    "-framework CoreVideo"
)
