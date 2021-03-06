cmake_minimum_required(VERSION 3.12)
project(Template VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

set(CMAKE_CXX_CLANG_TIDY
    "clang-tidy"
    "-extra-arg=-target" "-extra-arg=x86_64-pc-windows-gnu"
)

add_compile_options(
    -Weverything
    -Werror=return-type
    -Wno-c++98-compat
    -Wno-c++98-compat-pedantic
    -Wno-exit-time-destructors
    -Wno-global-constructors
    -Wno-missing-prototypes
    -Wno-missing-variable-declarations
    -Wno-padded
)

add_compile_definitions(
    _GLIBCXX_DEBUG
    _GLIBCXX_DEBUG_PEDANTIC
    _GLIBCXX_CONCEPT_CHECKS
)

add_executable(Template main.cpp)
