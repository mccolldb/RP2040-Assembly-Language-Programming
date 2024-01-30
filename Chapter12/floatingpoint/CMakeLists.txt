cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)
project(snippets C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

include_directories(${CMAKE_SOURCE_DIR})

add_executable(snippets1
  snippets.S 
)

pico_enable_stdio_uart(snippets1 1)
pico_enable_stdio_usb(snippets1 0)

pico_add_extra_outputs(snippets1)

target_link_libraries(snippets1 pico_stdlib)