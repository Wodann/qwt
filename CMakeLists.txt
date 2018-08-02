cmake_minimum_required(VERSION 3.1)
project(qwt VERSION 6.1.3 LANGUAGES CXX)

option(WITH_EXAMPLES "Whether to include examples" OFF)

add_subdirectory(src)
add_subdirectory(textengines)

if(WITH_EXAMPLES)
	add_subdirectory(examples)
endif()
