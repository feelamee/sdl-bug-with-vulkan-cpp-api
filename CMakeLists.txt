cmake_minimum_required(VERSION 3.5)
project(example)

add_executable(example "main.cpp")
target_compile_features(example PRIVATE cxx_std_20)

include(FetchContent)

set(VULKAN_HEADERS_ENABLE_MODULE OFF)
FetchContent_Declare(
  Vulkan-Headers
  GIT_REPOSITORY "https://github.com/KhronosGroup/Vulkan-Headers"
  GIT_TAG "v1.3.299")
FetchContent_MakeAvailable(Vulkan-Headers)

find_package(Vulkan REQUIRED)
target_link_libraries(example PRIVATE Vulkan::Headers vulkan)

FetchContent_Declare(
  SDL3
  GIT_REPOSITORY "https://github.com/libsdl-org/SDL"
  GIT_TAG "9493e6974f70a906950c9d8196c9a9982300f261")
FetchContent_MakeAvailable(SDL3)

target_link_libraries(example PRIVATE SDL3::SDL3)
