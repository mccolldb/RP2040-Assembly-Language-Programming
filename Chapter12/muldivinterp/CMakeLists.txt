cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)
project(snippets C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

include_directories(${CMAKE_SOURCE_DIR})

add_executable(snippets2
  snippets.S 
)

pico_enable_stdio_uart(snippets2 1)
pico_enable_stdio_usb(snippets2 0)

pico_add_extra_outputs(snippets2)

target_link_libraries(snippets2 pico_stdlib)