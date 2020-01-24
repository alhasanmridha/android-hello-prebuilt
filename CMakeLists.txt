cmake_minimum_required(VERSION 3.5)

project(client)

add_library(client STATIC 
    src/Hello.cpp
    include/hello.hpp
)
# Target system
set(CMAKE_SYSTEM_NAME  Android)

set(CMAKE_SYSTEM_VERSION 1)

#Please set the NDK_COMPILER_LOCATION appropriately
set(NDK_COMPILER_LOCATION /home/alhasan/Android/Sdk/ndk/21.0.6113669/toolchains/llvm/prebuilt/linux-x86_64/bin) #for armeabi system
# set(CMAKE_CXX_COMPILER ${NDK_COMPILER_LOCATION}/x86_64-linux-android23-clang++) #for x86_64 system
set(CMAKE_CXX_COMPILER ${NDK_COMPILER_LOCATION}/armv7a-linux-androideabi23-clang++)
target_include_directories(client
    PUBLIC 
        ${PROJECT_SOURCE_DIR}/include
)

