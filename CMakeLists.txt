project(BLPCONVERTER)
cmake_minimum_required(VERSION 2.6)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${BLPCONVERTER_BINARY_DIR}/bin")
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${BLPCONVERTER_BINARY_DIR}/lib")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${BLPCONVERTER_BINARY_DIR}/bin")

add_subdirectory(dependencies)

include_directories("${BLPCONVERTER_SOURCE_DIR}/dependencies/include/"
                    "${BLPCONVERTER_SOURCE_DIR}/dependencies/FreeImage/"
                    "${BLPCONVERTER_SOURCE_DIR}/dependencies/squish/"
)

add_executable(BLPConverter main.cpp blp.cpp)
target_link_libraries(BLPConverter freeimage squish)

set_target_properties(BLPConverter PROPERTIES COMPILE_DEFINITIONS "FREEIMAGE_LIB")
