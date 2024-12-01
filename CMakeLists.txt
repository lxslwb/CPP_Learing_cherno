cmake_minimum_required(VERSION 3.0)
project(CPP_L1)

# 设置C++标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 包含源文件目录
include_directories(src)

# 定义可执行文件
add_executable(MyApp
    src/main.cpp
    # 在此添加其他源文件
)

# 根据构建类型设置编译选项和其他相关配置
if (CMAKE_BUILD_TYPE STREQUAL "Debug")
    set(CMAKE_CXX_FLAGS_DEBUG "-g -O0")
    # 可以在这里添加其他仅在Debug模式下需要的配置，比如添加特定的库文件链接等
    # link_directories(debug_libs)
    # target_link_libraries(YourExecutableName DebugLibraryName)
elseif (CMAKE_BUILD_TYPE STREQUAL "Release")
    set(CMAKE_CXX_FLAGS_RELEASE "-O3")
    # 类似地，可添加仅在Release模式下需要的配置
    # link_directories(release_libs)
    # target_link_libraries(YourExecutableName ReleaseLibraryName)
endif ()