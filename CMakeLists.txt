cmake_minimum_required(VERSION 3.5)

# Force use of our custom partition table
set(PARTITION_TABLE_FILENAME "partitions.csv")

set(PROJECT_NAME "hackerhotel2024")

if(DEFINED ENV{PROJECT_VER})
    # Strip any preceding "v" from version (e.g. v1.1.1 → 1.1.1)
    message(INFO "Setting Project version!")
    string(REGEX REPLACE "v" "" PROJECT_VER "$ENV{PROJECT_VER}")
else()
    set(PROJECT_VER "999.999.999")
endif()

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(${PROJECT_NAME})
