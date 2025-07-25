cmake_minimum_required(VERSION 3.10)
project(MyProject C CXX)  # 同时支持C和C++
set(ProjName testapp)

# 指定使用Clang编译器
set(CMAKE_C_COMPILER "cl.exe")
set(CMAKE_CXX_COMPILER "cl.exe")

# 添加MSVC兼容性（关键！）
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} --target=x86_64-pc-windows-msvc")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} --target=x86_64-pc-windows-msvc")

# 设置C++标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 添加可执行文件
add_executable(${ProjName}
    main.cpp
)

# 包含目录
# target_include_directories(${ProjName} PRIVATE include)

# 链接库（如需要）
# target_link_libraries(${ProjName} PRIVATE some_library)
