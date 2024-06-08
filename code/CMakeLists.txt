cmake_minimum_required(VERSION 3.29)

project(engine3d LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++23")

find_package(OpenGL REQUIRED)

set(GLFW3_LIBRARY "${CMAKE_SOURCE_DIR}/glfw/lib/libglfw3.a")

set(SOURCE_FILES
    main.cpp
)

# Define your header files if necessary
set(HEADER_FILES
    # Add more header files as needed
)

# Define the link libraries
add_executable(${PROJECT_NAME})
target_sources(${PROJECT_NAME} PRIVATE ${SOURCE_FILES})

target_link_libraries(${PROJECT_NAME} ${GLFW3_LIBRARY} OpenGL::GL)
target_include_directories(${PROJECT_NAME} PRIVATE "${CMAKE_SOURCE_DIR}/glfw/include")
# Must be C++23 until CMake merges `import std` as a C++20 extension
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_23) 
