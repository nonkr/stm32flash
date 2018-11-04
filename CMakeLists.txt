cmake_minimum_required(VERSION 3.3.2)
project(stm32flash)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES
        dev_table.c
        i2c.c
        init.c
        main.c
        port.c
        serial_common.c
        serial_platform.c
        stm32.c
        utils.c
        )

add_subdirectory(parsers)

add_executable(stm32flash ${SOURCE_FILES})

target_link_libraries(stm32flash parsers)
