cmake_minimum_required(VERSION 3.27)

project(VulkanTestProject)
set(CMAKE_CXX_STANDARD 17)

set(PROJECT_DIR ${CMAKE_SOURCE_DIR})
set(PROJECT_Lib_DIR ${PROJECT_DIR}/lib)
set(PROJECT_SRC_DIR ${PROJECT_DIR}/src)
add_executable(${PROJECT_NAME} ${PROJECT_SRC_DIR}/main.cpp)

find_package(Vulkan REQUIRED)
add_subdirectory(${PROJECT_Lib_DIR}/glfw)
add_subdirectory(${PROJECT_Lib_DIR}/glm)

target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)
target_link_libraries(${PROJECT_NAME} glfw)
target_link_libraries(${PROJECT_NAME} glm)
