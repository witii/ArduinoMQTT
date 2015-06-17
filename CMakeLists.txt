set(CMAKE_TOOLCHAIN_FILE ~/Dev/github/energia-cmake/cmake/EnergiaToolchain.cmake)

cmake_minimum_required(VERSION 3.1)
project(ArduinoMQTT)

set(CMAKE_VERBOSE_MAKEFILE on)

set(ENERGIA_DEFAULT_BOARD witii_cc3200)
#set(ENERGIA_DEFAULT_PORT /dev/tty.usbserial-cc3101B)
set(ENERGIA_DEFAULT_PORT /dev/tty.usbserial-AI02S970)

file(GLOB SOURCE_FILES
    utility/*
    *.h
    *.cpp)

generate_energia_library(ArduinoMQTT
    SRCS ${SOURCE_FILES})

generate_energia_firmware(Hello
    SKETCH examples/Hello/Hello.ino)
