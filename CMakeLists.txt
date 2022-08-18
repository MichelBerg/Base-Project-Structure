# Base Configuration
cmake_minimum_required(VERSION "3.16.3")
set(CMAKE_CXX_STANDARD 17) # USING C++ Standard 2017 (necessarry for filesytem)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
add_compile_options(-ggdb -pthread)

# The Project
project(main VERSION 1.0) # Name of the Project

# Linking Lib TODO
# add_library(mylib STATIC lib/boo.cpp)
# target_include_directories(mylib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/lib/include)
# target_link_libraries(${PROJECT_NAME} PUBLIC mylib)

# Linking Normal
file(GLOB_RECURSE SRC_FILES src/*.cpp) # Searches recurse within all .cpp files in the src directory
add_executable(${PROJECT_NAME} main.cpp ${SRC_FILES})
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include) # Give info about the include directories



# Libraries
target_link_libraries(${PROJECT_NAME} PRIVATE pigpio) # include pigpio Lib