# CMake Target Resources

## Offline Setup

There are multiple ways you can do this.
1. simply download the file once and place it into your project
2. create a git submodule

If you always want to have the newest version of this utility, the git submodule or the [online version](#Online Setup) is prefered.

## Online Setup

To use always the latest version of this utility, it is possible to just download it.

Here is a template for doing exactly this.
Notice that you will need an internet connection on the first cmake run!

cmake/default_target_compile_options.cmake:
```cmake
cmake_minimum_required(VERSION 3.18)

if (NOT EXISTS ${CMAKE_BINARY_DIR}/default_target_compile_options.cmake)

    file(DOWNLOAD
         https://raw.githubusercontent.com/rawbby/CMakeTargetCompileOptions20/master/default_target_compile_options.cmake
         ${CMAKE_BINARY_DIR}/default_target_compile_options.cmake
         TLS_VERIFY ON)

endif ()

include(${CMAKE_BINARY_DIR}/default_target_compile_options.cmake)
```
