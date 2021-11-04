CMAKE_MINIMUM_REQUIRED(VERSION 3.16)
project(mybrary C)
set(CMAKE_C_STANDARD 99)

if (MSVC)
    SET(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS TRUE)
endif()

file(GLOB SOURCES *.c)

include_directories(./)

# Create shared library
add_library(${PROJECT_NAME} SHARED ${SOURCES})
ADD_LIBRARY(mybrary_static STATIC ${SOURCES})

install(TARGETS ${PROJECT_NAME} DESTINATION build)

file(GLOB HEADERS ./*.h)
install(FILES ${HEADERS} DESTINATION ./)