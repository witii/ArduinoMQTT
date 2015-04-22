set(CMAKE_TOOLCHAIN_FILE ~/Dev/github/energia-cmake/cmake/EnergiaToolchain.cmake)

cmake_minimum_required(VERSION 3.1)
project(OxMqtt)

set(CMAKE_VERBOSE_MAKEFILE on)

file(GLOB SOURCE_FILES
    utility/*
    src/*
    OxMqtt.h
    OxMqtt.cpp)


generate_energia_library(OxMqtt
    SRCS ${SOURCE_FILES}
    BOARD lpcc3200)

generate_energia_firmware(Hello
    SRCS examples/Hello/Hello.cpp
    LIBS OxMqtt
    BOARD lpcc3200
    PORT /dev/tty.usbserial-cc3101B)
