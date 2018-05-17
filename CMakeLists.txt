cmake_minimum_required (VERSION 3.0)
set (CMAKE_CXX_STANDARD 11)
project (gamma)

macro(add_example NAME)
add_executable(${NAME} ${NAME}.cpp)
target_link_libraries(${NAME} gamma audio_io)
endmacro()

find_library(SND_LIBRARY
    NAMES snd sndfile
    HINTS "external/lib_osx"
)
if (NOT SND_LIBRARY)
    message(FATAL_ERROR "snd not found")
endif()

#link_directories(external/lib_osx)

include_directories(.)
include_directories(external/include)

add_subdirectory(src)
add_subdirectory(examples)
