cmake_minimum_required(VERSION 2.8)

project(oui C)

add_definitions(-O -Wall -Werror --std=gnu99 -D_GNU_SOURCE)

add_library(oui MODULE oui.c)
include_directories(../../../staging_dir/target-arm-linux-gnueabi_glibc/usr/include)
target_link_libraries(oui crypt)
set_target_properties(oui PROPERTIES OUTPUT_NAME oui PREFIX "")

install(TARGETS oui
    LIBRARY DESTINATION lib/lua/
)
