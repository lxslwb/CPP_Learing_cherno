cmake_minimum_required(VERSION 3.0)
project(CPP_L1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(src)

add_executable(MyApp
    src/main.cpp
    # 在这里添加其他源文件，如src/other_file.cpp
)

set_target_properties(MyApp PROPERTIES
    COMPILE_FLAGS -g
)

set(CMAKE_CXX_FLAGS_DEBUG "-O0")