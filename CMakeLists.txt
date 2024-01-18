cmake_minimum_required(VERSION 3.16 FATAL_ERROR)

project(ROOTFetchContent LANGUAGES CXX)

set(FETCHCONTENT_QUIET FALSE)
include(FetchContent)

set(ROOT_URL "https://github.com/flagarde/root.git")
set(ROOT_TAG "FetchContent")
set(testing OFF)
set(roottest OFF)
set(FETCHCONTENT_QUIET FALSE)
FetchContent_Declare(ROOT GIT_REPOSITORY "${ROOT_URL}" GIT_TAG "${ROOT_TAG}" GIT_PROGRESS TRUE)

FetchContent_MakeAvailable(ROOT)

add_executable(main main.cpp)
target_link_libraries(main PRIVATE ROOT::Core)
