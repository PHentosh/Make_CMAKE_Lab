CMAKE_MINIMUM_REQUIRED(VERSION 3.16)
project(examples C)
set(CMAKE_C_STANDARD 99)


add_executable(example example.c)

find_library(MYCUSTOMLIB mybrary PATH ../library/build NO_DEFAULT_PATH)

target_include_directories(example PUBLIC ../library)
target_link_libraries(example ${MYCUSTOMLIB})

