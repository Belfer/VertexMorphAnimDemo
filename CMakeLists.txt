cmake_minimum_required(VERSION 2.8)

project(MorphAnimDemo)
set(${PROJECT_NAME}_MAJOR_VERSION 0)
set(${PROJECT_NAME}_MINOR_VERSION 1)
set(${PROJECT_NAME}_REVISION_VERSION 1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -Wall")

add_compile_definitions (RESOURCE_PATH="${CMAKE_CURRENT_SOURCE_DIR}/res")

add_subdirectory(extern)
add_subdirectory(src)

include_directories(src
    ${DEPENDENCIES_INCLUDE}
)

add_executable(${PROJECT_NAME} ${CLIENT_HDRS} ${CLIENT_SRCS})

target_link_libraries(${PROJECT_NAME}
    ${DEPENDENCIES_LIBS}
)
