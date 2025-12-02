cmake_minimum_required(VERSION 3.15)
project(ifqoi VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(MSVC)
    add_compile_options(/W4 /utf-8)
    add_compile_definitions(_CRT_SECURE_NO_WARNINGS)
else()
    add_compile_options(-Wall -Wextra -pedantic)
endif()

include_directories(${CMAKE_SOURCE_DIR}/include)

set(SOURCES
    src/ifqoi.cpp
    src/qoi_decoder.cpp
)

set(HEADERS
    include/susie.h
    include/qoi.h
)

add_library(ifqoi SHARED
    ${SOURCES}
    ${HEADERS}
)

set_target_properties(ifqoi PROPERTIES
    OUTPUT_NAME "ifqoi"
    PREFIX ""
    SUFFIX ".sph"
)

if(MSVC)
    set_target_properties(ifqoi PROPERTIES
        LINK_FLAGS "/DEF:${CMAKE_SOURCE_DIR}/ifqoi.def"
    )
endif()

install(TARGETS ifqoi
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
)
