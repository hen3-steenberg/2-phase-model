cmake_minimum_required(VERSION 3.30)

project(HIP CXX)

enable_language(HIP)

set(CMAKE_HIP_STANDARD 23)
set(CMAKE_HIP_EXTENSIONS OFF)
set(CMAKE_HIP_STANDARD_REQUIRED ON)

set(ROCM_ROOT "opt/rocm")

list(APPEND CMAKE_PREFIX_PATH "${ROCM_ROOT}")

set(CMAKE_HIP_ARCHITECTURES gfx1201)

add_executable(test main.hip)

set_source_files_properties(main.hip PROPERTIES LANGUAGE HIP)
