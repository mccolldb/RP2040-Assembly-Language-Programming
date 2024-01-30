cmake_minimum_required(VERSION 3.12)

# Pull in SDK (must be before project)
include(pico_sdk_import.cmake)

project(pico_examples C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

set(PICO_EXAMPLES_PATH ${PROJECT_SOURCE_DIR})

# Initialize the SDK
pico_sdk_init()

include(example_auto_set_url.cmake)
add_subdirectory(Chapter2)
add_subdirectory(Chapter4)
add_subdirectory(Chapter5)
add_subdirectory(Chapter6)
#add_subdirectory(Chapter7)
add_subdirectory(Chapter8/1)
add_subdirectory(Chapter8/2)
add_subdirectory(Chapter8/3)
add_subdirectory(Chapter9)
add_subdirectory(Chapter10/1)
add_subdirectory(Chapter10/2)
add_subdirectory(Chapter10/3)
add_subdirectory(Chapter10/4)
add_subdirectory(Chapter10/5)
add_subdirectory(Chapter11)
add_subdirectory(Chapter12/floatingpoint)
add_subdirectory(Chapter12/muldivinterp)
add_subdirectory(Chapter13/multicore)
add_subdirectory(Chapter13/spinlocks)
add_subdirectory(Chapter14)


add_compile_options(-Wall
        -Wno-format          # int != int32_t as far as the compiler is concerned because gcc has int32_t as long int
        -Wno-unused-function # we have some for the docs that aren't called
        -Wno-maybe-uninitialized
        )
