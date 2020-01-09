cmake_minimum_required(VERSION 3.10)

set(CMAKE_PREFIX_PATH "/tmp")

project(hello)

include_directories("include")
file(GLOB SOURCES "src/hw_main.c")

add_library(lib STATIC src/hw_hello.c src/hw_power.c)
target_link_libraries(lib)

add_executable(hello ${SOURCES})
target_link_libraries(hello lib)
install (TARGETS lib DESTINATION /tmp/lib)	
install (TARGETS hello DESTINATION ${CMAKE_PREFIX_PATH})
