cmake_minimum_required(VERSION 3.5)

cmake_policy(SET CMP0040 NEW)
cmake_policy(SET CMP0072 NEW)

file (STRINGS "VERSION" APP_VERSION)

project(DummyGitHubProject VERSION "${APP_VERSION}" LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS ON)

file(GLOB_RECURSE PROJ_SRC src/*.h src/*.cpp)

add_executable(DummyGitHubProject ${PROJ_SRC})

target_link_libraries(DummyGitHubProject)

add_custom_target(Other SOURCES
    VERSION LICENCE README.md
)
