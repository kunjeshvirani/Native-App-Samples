
####### CMake script by kv
####### Created on 7 february, 2017

cmake_minimum_required(VERSION 3.4.1)
set(NDK_SRCS ${ANDROID_NDK}/sources/android/native_app_glue/android_native_app_glue.c)
add_library(app-glue STATIC  ${NDK_SRCS})
add_library(native-lib
            SHARED
            src/main/cpp/native-lib.cpp
                              )

target_include_directories(native-lib PRIVATE
                           ${ANDROID_NDK}/sources/android/native_app_glue)
target_link_libraries(native-lib
                    log
                    android
                    app-glue
                   )
