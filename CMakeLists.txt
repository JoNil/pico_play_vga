cmake_minimum_required(VERSION 3.12)

set(PICO_SDK_PATH ../../pico-sdk)

# Pull in PICO SDK (must be before project)
include(pico_sdk_import.cmake)

# We also need PICO EXTRAS
include(pico_extras_import.cmake)

project(pico_play_vga C CXX)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialize the Pico SDK
pico_sdk_init()

add_executable(pico_play_vga
        src/main.c)


target_link_libraries(pico_play_vga PRIVATE
        pico_multicore
        pico_stdlib
        pico_scanvideo_dpi)
pico_add_extra_outputs(pico_play_vga)