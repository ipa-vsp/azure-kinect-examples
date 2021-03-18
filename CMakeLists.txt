cmake_minimum_required(VERSION 3.9.0)

cmake_policy(SET CMP0048 NEW)

project(k4a_examples)

find_package(k4a REQUIRED)

if (OpenCV_REQUIRED)
    find_package(OpenCV REQUIRED)
else()
    find_package(OpenCV)
endif ()

if (OpenCV_FOUND)
    if ("${CMAKE_SYSTEM_NAME}" STREQUAL "Windows")
        file(COPY ${OpenCV_DIR}/../bin/ DESTINATION ${CMAKE_RUNTIME_OUTPUT_DIRECTORY} FILES_MATCHING PATTERN "*.dll")
    endif ()
endif ()

add_subdirectory(extern)
add_subdirectory(opengl_viewer)