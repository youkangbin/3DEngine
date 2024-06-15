cmake_minimum_required(VERSION 3.29)

project(engine3d LANGUAGES CXX C)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++23")

find_package(OpenGL REQUIRED)

set(CMAKE_DEPENDS_USE_COMPILER FALSE)

# Define the link libraries
add_executable(${PROJECT_NAME} 
    "main.cpp"
    "glad/src/glad.c"
)

target_include_directories(${PROJECT_NAME} PRIVATE 
    "glfw/include"
    "glad/include"
)

target_link_libraries(${PROJECT_NAME} 
"${CMAKE_SOURCE_DIR}/glfw/lib/libglfw3.a"
 OpenGL::GL)
