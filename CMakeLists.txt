# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.8)

project ("vkRasterization")

set (CMAKE_CXX_STANDARD 17)
set (CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}/bin)

set (SRC_FILES
	${CMAKE_SOURCE_DIR}/src/vkRasterization.cpp
)

set (INCLUDE_DIR
	${CMAKE_SOURCE_DIR}/include
	${CMAKE_SOURCE_DIR}/external/egaf/include
)

add_subdirectory(external/egaf)
 
add_executable (vkRasterization ${SRC_FILES})

target_include_directories(vkRasterization PUBLIC ${INCLUDE_DIR})
target_link_libraries(vkRasterization egaf)